---
title: Aktivieren der Netzwerkablaufverfolgung
ms.date: 03/30/2017
helpviewer_keywords:
- trace destinations
- sending traces to log file
- trace listeners, network tracing
- network tracing, enabling
- CLR Debugger
- default listeners
- logs, trace
- destination for tracing output
ms.assetid: 5fff458c-51a6-4134-ba47-8a6137ddc41e
author: mcleblanc
ms.author: markl
manager: markl
ms.openlocfilehash: 56a24f93e92fbfbd2dbb1156a1c3ef786f59034e
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33390460"
---
# <a name="enabling-network-tracing"></a>Aktivieren der Netzwerkablaufverfolgung
Die Netzwerkablaufverfolgung bietet Zugriff auf Informationen über den Aufruf von Methoden sowie Informationen zu dem von einer Anwendung generierten Netzwerkdatenverkehr. Sie müssen folgende Aufgaben abschließen, um die Netzwerkablaufverfolgung in Ihrer Anwendung zu aktivieren:  
  
-   Kompilieren Sie Ihren Code, während die Ablaufverfolgung aktiviert ist. Weitere Informationen zu den erforderlichen Compilerschaltern, um die Ablaufverfolgung zu aktivieren, finden Sie unter [How to: Compile Conditionally with Trace and Debug (Vorgehensweise: Bedingtes Kompilieren mit Ablaufverfolgung und Debuggen)](../../../docs/framework/debug-trace-profile/how-to-compile-conditionally-with-trace-and-debug.md).  
  
-   Geben Sie ein Ziel für die Ablaufsverfolgungsausgabe an.  
  
-   Konfigurieren Sie das Verhalten der Netzwerkablaufverfolgung. Ausführliche Informationen finden Sie unter [How to: Configure Network Tracing (Vorgehensweise: Konfigurieren der Netzwerkablaufverfolgung)](../../../docs/framework/network-programming/how-to-configure-network-tracing.md).  
  
 Die am häufigsten verwendeten Ziele für die Ablaufverfolgung, die auch als Ablaufverfolgungslistener bezeichnet werden, sind der Standardlistener und die Protokolldatei.  
  
 Die Ablaufverfolgung verwendet den Standardlistener, wenn Sie keinen Ablaufverfolgungslistener angeben. Sie können Nachrichten anzeigen, die an den Standardlistener gesendet werden, indem Sie Ihren Code in einem Debugger für verwalteten Code ausführen, zum Beispiel im CLR-Debugger, der in der .NET Framework SDK enthalten ist oder in „DBwin32.exe“, die in Windows SDK enthalten ist. Verwenden Sie den CLR-Debugger, die Ablaufverfolgungsmeldungen werden im Fenster **Ausgabe** angezeigt.  
  
 Wenn Sie es bevorzugen, eine Datei zu verwenden, um Ablaufverfolgungen zu erhalten, können Sie mithilfe der Konfigurationseinstellungen, wie im folgenden Beispiel gezeigt, eine Protokolldatei angeben. (Eine allgemeine Beschreibung der Konfigurationsdateien finden Sie unter [Configuration Files (Konfigurationsdatei)](../../../docs/framework/configure-apps/index.md).)  
  
 Fügen Sie folgenden Knoten zum `<system.diagnostics>`-Knoten der entsprechenden Konfigurationsdatei (Anwendung oder Computer) hinzu, um Ablaufverfolgungen an eine Protokolldatei zu senden. Sie können den Namen der Datei (trace.log) Ihren Anforderungen entsprechend ändern.  
  
```xml  
<system.diagnostics>  
  <trace autoflush="true" indentsize="4">  
    <listeners>  
      <add name="file" type="System.Diagnostics.TextWriterTraceListener" initializeData="trace.log"/>  
    </listeners>   
  </trace>  
</system.diagnostics>  
```  
  
## <a name="see-also"></a>Siehe auch  
 [Interpretieren von Netzwerkablaufverfolgung](../../../docs/framework/network-programming/interpreting-network-tracing.md)  
 [Netzwerkablaufverfolgung in .NET Framework](../../../docs/framework/network-programming/network-tracing.md)  
 [Einführung in Instrumentation und Ablaufverfolgung](http://msdn.microsoft.com/library/e924e57c-33cf-4b0e-9e7f-a45d13e38f2c)
