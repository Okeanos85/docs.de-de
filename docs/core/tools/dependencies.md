---
title: Verwalten von Abhängigkeiten in .NET Core-Tools
description: Erläutert, wie Abhängigkeiten mit den .NET Core-Tools verwaltet werden können.
author: blackdwarf
ms.author: mairaw
ms.date: 03/06/2017
ms.openlocfilehash: c8f40b8571523b98da55b047fea8d2bf03b390a2
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33213661"
---
# <a name="managing-dependencies-with-net-core-sdk-10"></a>Verwalten von Abhängigkeiten mit .NET Core SDK 1.0

Mit dem Wechsel von .NET Core-Projekten von „project.json“ zu „csproj“ und MSBuild wurde auch ein beträchtlicher Aufwand betrieben, der zu einer Vereinheitlichung der Projektdatei und Objekte geführt hat, sodass Abhängigkeiten nachverfolgt werden können. Bei .NET Core-Projekten ist dies mit der Verwendung von „project.json“ vergleichbar. Es gibt keine separate JSON- oder XML-Datei, die NuGet-Abhängigkeiten nachverfolgt. Mit dieser Änderung haben wir auch eine andere Art von *Verweis* in die CSPROJ-Syntax eingeführt: `<PackageReference>`. 

In diesem Dokument wird der neue Verweistyp beschrieben. Es wird außerdem gezeigt, wie mit diesem neuen Verweistyp eine Paketabhängigkeit zum Projekt hinzugefügt wird. 

## <a name="the-new-packagereference-element"></a>Das neue \<PackageReference>-Element
`<PackageReference>` weist die folgende grundlegende Struktur auf:

```xml
<PackageReference Include="PACKAGE_ID" Version="PACKAGE_VERSION" />
```

Wenn Sie mit MSBuild vertraut sind, kommt es Ihnen durch bereits vorhandene Verweistypen bekannt vor. Der Schlüssel ist die `Include`-Anweisung, mit der die Paket-ID angegeben wird, die Sie dem Projekt hinzufügen möchten. Das untergeordnete `<Version>`-Element gibt die abzurufende Version an. Die Versionen werden gemäß den [NuGet-Versionsregeln](/nuget/create-packages/dependency-versions#version-ranges) angegeben.

> [!NOTE]
> Wenn Ihnen die allgemeine `csproj`-Syntax noch unbekannt ist, finden Sie weitere Informationen in der Dokumentation zu [MSBuild-Projektverweisen](/visualstudio/msbuild/msbuild-project-file-schema-reference).  

Beim Hinzufügen einer Abhängigkeit, die nur für ein bestimmtes Ziel verfügbar ist, werden Bedingungen wie im folgenden Beispiel verwendet:

```xml
<PackageReference Include="PACKAGE_ID" Version="PACKAGE_VERSION" Condition="'$(TargetFramework)' == 'netcoreapp1.0'" />
```

Der obige Code bedeutet, dass die Abhängigkeit nur gültig ist, wenn der Build für das angegebene Ziel erstellt wird. `$(TargetFramework)` in der Bedingung ist eine MSBuild-Eigenschaft, die im Projekt festgelegt wird. Bei den gängigsten .NET Core-Anwendungen ist dies nicht erforderlich. 

## <a name="adding-a-dependency-to-your-project"></a>Hinzufügen einer Abhängigkeit zu Ihrem Projekt
Es ist einfach, eine Abhängigkeit zu Ihrem Projekt hinzuzufügen. Im folgenden Beispiel wird das Hinzufügen der Json.NET-Version `9.0.1` zu Ihrem Projekt veranschaulicht. Natürlich gilt dies für alle anderen NuGet-Abhängigkeiten. 

Wenn Sie Ihre Projektdatei öffnen, sehen Sie zwei oder mehr `<ItemGroup>`-Knoten. Sie werden feststellen, dass einer der Knoten bereits `<PackageReference>`-Elemente aufweist. Sie können Ihre neue Abhängigkeit zu diesem Knoten hinzufügen oder eine neue erstellen. Sie können frei entscheiden, da das Ergebnis gleich sein wird. 

In diesem Beispiel verwenden wir die Standardvorlage, die von `dotnet new console` abgelegt wird. Dies ist eine einfache Konsolenanwendung. Wenn wir das Projekt öffnen, suchen wir zuerst nach `<ItemGroup>` mit dem bereits vorhandenen `<PackageReference>`-Element. Wir fügen dann Folgendes hinzu:

```xml
<PackageReference Include="Newtonsoft.Json" Version="9.0.1" />
```
Anschließend speichern wir das Projekt und führen den Befehl `dotnet restore` aus, um die Abhängigkeit zu installieren. 

[!INCLUDE[DotNet Restore Note](~/includes/dotnet-restore-note.md)]

Das vollständige Projekt sieht folgendermaßen aus:

```xml
<Project Sdk="Microsoft.NET.Sdk">
  <PropertyGroup>
    <OutputType>Exe</OutputType>
    <TargetFramework>netcoreapp1.0</TargetFramework>
  </PropertyGroup>

  <ItemGroup>
    <PackageReference Include="Newtonsoft.Json" Version="9.0.1" />
  </ItemGroup>
</Project>
```

## <a name="removing-a-dependency-from-the-project"></a>Entfernen einer Abhängigkeit aus dem Projekt
Das Entfernen einer Abhängigkeit aus der Projektdatei bedeutet einfach, `<PackageReference>` aus der Projektdatei zu entfernen.
