---
title: Speichern der Ergebnisse einer Abfrage im Speicher
description: So speichern Sie Ergebnisse.
ms.date: 11/30/2016
ms.assetid: 5b863961-1750-4cf9-9607-acea5054d15a
ms.openlocfilehash: c125d134d7c1db98363844c12fc8abd3faa9c868
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33279632"
---
# <a name="store-the-results-of-a-query-in-memory"></a>Speichern der Ergebnisse einer Abfrage im Speicher

Eine Abfrage besteht im Grunde aus einer Reihe von Anweisungen für das Abrufen und Organisieren von Daten. Abfragen werden verzögert ausgeführt, da jedes nachfolgende Element im Ergebnis angefordert wird. Wenn Sie `foreach` zum Durchlaufen der Ergebnisse verwenden, werden Elemente so zurückgegeben, wie auf sie zugegriffen wurde. Rufen Sie einfach eine der folgenden Methoden für die Abfragevariable auf, um eine Abfrage auszuwerten und ihre Ergebnisse ohne das Ausführen einer `foreach`-Schleife zu speichern:  
  
-   <xref:System.Linq.Enumerable.ToList%2A>  
  
-   <xref:System.Linq.Enumerable.ToArray%2A>  
  
-   <xref:System.Linq.Enumerable.ToDictionary%2A>  
  
-   <xref:System.Linq.Enumerable.ToLookup%2A>  
  
 Es wird empfohlen, dass Sie die zurückgegebenen Auflistungsobjekte beim Speichern der Abfrageergebnisse einer neuen Variable zuweisen, wie im folgenden Beispiel gezeigt wird:  
  
## <a name="example"></a>Beispiel  
 [!code-csharp[csProgGuideLINQ#25](../../../samples/snippets/csharp/concepts/linq/how-to-store-the-results-of-a-query-in-memory_1.cs)]  
  

## <a name="see-also"></a>Siehe auch  
 [LINQ-Abfrageausdrücke](index.md)
