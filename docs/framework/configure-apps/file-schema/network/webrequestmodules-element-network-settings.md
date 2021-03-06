---
title: '&lt;WebRequestModules&gt; -Element (Netzwerkeinstellungen)'
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.net/webRequestModules
- http://schemas.microsoft.com/.NetConfiguration/v2.0#webRequestModules
helpviewer_keywords:
- webRequestModules element
- <webRequestModules> element
ms.assetid: 1263de11-3e0a-4f94-97c9-710b2ae53817
author: mcleblanc
ms.author: markl
manager: markl
ms.openlocfilehash: 7454099d8af0f2d656296be55677c648cc0c36c9
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
ms.locfileid: "32742691"
---
# <a name="ltwebrequestmodulesgt-element-network-settings"></a>&lt;WebRequestModules&gt; -Element (Netzwerkeinstellungen)
Gibt die Module zu verwenden, um Informationen von Netzwerkhosts anfordern.  
  
 \<configuration>  
\<system.net>  
\<webRequestModules>  
  
## <a name="syntax"></a>Syntax  
  
```xml  
<webRequestModules>   
</webRequestModules>  
```  
  
## <a name="attributes-and-elements"></a>Attribute und Elemente  
 In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.  
  
### <a name="attributes"></a>Attribute  
 Keine  
  
### <a name="child-elements"></a>Untergeordnete Elemente  
  
|**Element**|**Beschreibung**|  
|-----------------|---------------------|  
|[add](../../../../../docs/framework/configure-apps/file-schema/network/add-element-for-webrequestmodules-network-settings.md)|Fügt eine benutzerdefinierte Webmodul der Anforderung an die Anwendung an.|  
|[clear](../../../../../docs/framework/configure-apps/file-schema/network/clear-element-for-webrequestmodules-network-settings.md)|Entfernt alle registrierten Anforderung Webmodule aus der Anwendung an.|  
|[remove](../../../../../docs/framework/configure-apps/file-schema/network/remove-element-for-webrequestmodules-network-settings.md)|Entfernt ein benutzerdefiniertes Web-Request-Modul aus der Anwendung an.|  
  
### <a name="parent-elements"></a>Übergeordnete Elemente  
  
|**Element**|**Beschreibung**|  
|-----------------|---------------------|  
|[System.NET](../../../../../docs/framework/configure-apps/file-schema/network/system-net-element-network-settings.md)|Enthält Einstellungen, die festlegen, wie Verbindungen zwischen .NET Framework und dem Netzwerk hergestellt werden.|  
  
## <a name="remarks"></a>Hinweise  
 Die `webRequestModules` Element registriert Nachfolger der <xref:System.Net.WebRequest> -Klasse zur Verarbeitung von Anforderungen für Objektinformationen zu Hosts im Netzwerk. Anforderung Webmodule implementieren müssen die <xref:System.Net.IWebRequestCreate> Schnittstelle.  
  
 .NET Framework enthält die Anforderung Webmodule für URIs, die mit http://, https:// und file:// beginnen. Sie können die Standardmodule nur durch Registrieren eines benutzerdefinierten Moduls in der Konfigurationsdatei überschreiben.  
  
## <a name="configuration-files"></a>Konfigurationsdateien  
 Dieses Element kann in der Anwendungskonfigurationsdatei oder in der Computerkonfigurationsdatei ("Machine.config") verwendet werden.  
  
## <a name="example"></a>Beispiel  
 Im folgende Beispiel wird die Standard-HTTP-Modul registriert. Sie sollten die Werte für Version und PublicKeyToken durch die richtigen Werte für das angegebene Modul ersetzen.  
  
```xml  
<configuration>  
  <system.net>  
    <webRequestModules>  
      <add prefix="http"  
           type="System.Net.HttpRequestCreator, System, Version=2.0.3600.0,  
           Culture=neutral, PublicKeyToken=b77a5c561934e089"  
      />  
    </webRequestModules>  
  </system.net>  
</configuration>  
```  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.Net.WebRequest>  
 <xref:System.Net.IWebRequestCreate>  
 [Network Settings Schema (Schema für Netzwerkeinstellungen)](../../../../../docs/framework/configure-apps/file-schema/network/index.md)
