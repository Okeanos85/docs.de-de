---
title: Microsoft.Transactions.TransactionBridge.EnlistTransactionFailure
ms.date: 03/30/2017
ms.assetid: 1b9f5139-e122-4716-9ef7-2f38e1813993
ms.openlocfilehash: 9dd2ba5a3e94ff794d4b8a8775944355b105f790
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33482007"
---
# <a name="microsofttransactionstransactionbridgeenlisttransactionfailure"></a>Microsoft.Transactions.TransactionBridge.EnlistTransactionFailure
Der WS-AT-Protokolldienst konnte sich nicht auf einer Transaktion mit dem bereitgestellten Koordinationskontext eintragen.  
  
## <a name="description"></a>Beschreibung  
 Wird nachverfolgt, wenn MSDTC sich nicht auf einer Transaktion für ein gegebenes 2pc-Protokoll eintragen konnte.  Dies kann geschehen, wenn die Transaktion nicht mehr existiert, die Eintragung nicht mehr erlaubt ist oder zu viele Eintragungen vorhanden sind.  
  
## <a name="troubleshooting"></a>Problembehandlung  
 Überprüfen Sie die Statuszeichenfolge innerhalb der Ablaufverfolgungsnachricht, um zu bestimmen, ob ein ausführbares Element vorhanden ist.  
  
## <a name="see-also"></a>Siehe auch  
 [Ablaufverfolgung](../../../../../docs/framework/wcf/diagnostics/tracing/index.md)  
 [Verwenden der Ablaufverfolgung zum Beheben von Anwendungsfehlern](../../../../../docs/framework/wcf/diagnostics/tracing/using-tracing-to-troubleshoot-your-application.md)  
 [Verwaltung und Diagnose](../../../../../docs/framework/wcf/diagnostics/index.md)
