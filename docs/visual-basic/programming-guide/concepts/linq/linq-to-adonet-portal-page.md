---
title: LINQ to ADO.NET (Portalseite)
ms.date: 07/20/2015
ms.assetid: bbbd7c76-2981-4b91-b8d2-437547181f52
ms.openlocfilehash: 1f8985f6fa86ec906b4495fe15f2936af4270e79
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33646564"
---
# <a name="linq-to-adonet-portal-page"></a>LINQ to ADO.NET (Portalseite)
Mit [!INCLUDE[linq_adonet](~/includes/linq-adonet-md.md)] können Sie in [!INCLUDE[vstecado](~/includes/vstecado-md.md)] mithilfe des Programmiermodells [!INCLUDE[vbteclinqext](~/includes/vbteclinqext-md.md)] jedes aufzählbare Objekt abfragen.  
  
> [!NOTE]
>  Die [!INCLUDE[linq_adonet](~/includes/linq-adonet-md.md)]-Dokumentation befindet sich im Abschnitt „ADO.NET“ des .NET Framework SDK: [LINQ und ADO.NET](http://msdn.microsoft.com/library/bf0c8f93-3ff7-49f3-8aed-f2b7ac938dec).  
  
 Es gibt drei separate ADO.NET-[!INCLUDE[vbteclinqext](~/includes/vbteclinqext-md.md)]-Technologien: [!INCLUDE[linq_dataset](~/includes/linq-dataset-md.md)], [!INCLUDE[vbtecdlinq](~/includes/vbtecdlinq-md.md)] und [!INCLUDE[linq_entities](~/includes/linq-entities-md.md)]. [!INCLUDE[linq_dataset](~/includes/linq-dataset-md.md)] ermöglicht umfangreichere, optimierte Abfragen von <xref:System.Data.DataSet>. [!INCLUDE[vbtecdlinq](~/includes/vbtecdlinq-md.md)] ermöglicht Ihnen SQL Server-Datenbankschemas direkt abzufragen, und mit [!INCLUDE[linq_entities](~/includes/linq-entities-md.md)] können Sie das [!INCLUDE[adonet_edm](~/includes/adonet-edm-md.md)] abfragen.  
  
## <a name="linq-to-dataset"></a>LINQ to DataSet  
 <xref:System.Data.DataSet> ist eine der am häufigsten verwendeten Komponenten in [!INCLUDE[vstecado](~/includes/vstecado-md.md)] und ein Schlüsselelement des getrennten Programmiermodells, auf dem [!INCLUDE[vstecado](~/includes/vstecado-md.md)] aufgebaut ist. Trotz seiner Bedeutung sind die Abfragefunktionen des <xref:System.Data.DataSet> begrenzt.  
  
 Mit [!INCLUDE[linq_dataset](~/includes/linq-dataset-md.md)] können Sie umfangreichere Abfragefunktionen in <xref:System.Data.DataSet> integrieren, indem Sie die gleiche Abfragefunktionalität verwenden, die für viele andere Datenquellen verfügbar ist.  
  
 Weitere Informationen finden Sie unter [LINQ to DataSet](../../../../framework/data/adonet/linq-to-dataset.md).  
  
## <a name="linq-to-sql"></a>LINQ to SQL  
 [!INCLUDE[vbtecdlinq](~/includes/vbtecdlinq-md.md)] stellt eine Laufzeitinfrastruktur zum Verwalten relationaler Daten als Objekte bereit. In [!INCLUDE[vbtecdlinq](~/includes/vbtecdlinq-md.md)] wird das Datenmodell einer relationalen Datenbank einem Objektmodell zugeordnet, das in der Programmiersprache des Entwicklers ausgedrückt ist. Wenn Sie die Anwendung ausführen, übersetzt [!INCLUDE[vbtecdlinq](~/includes/vbtecdlinq-md.md)] die sprachintegrierten Abfragen im Objektmodell in SQL und sendet sie zur Ausführung an die Datenbank. Wenn die Datenbank die Ergebnisse zurückgibt, übersetzt [!INCLUDE[vbtecdlinq](~/includes/vbtecdlinq-md.md)] die Ergebnisse zurück in Objekte, die Sie bearbeiten können.  
  
 [!INCLUDE[vbtecdlinq](~/includes/vbtecdlinq-md.md)] bietet Unterstützung für gespeicherte Prozeduren und benutzerdefinierte Funktionen in der Datenbank sowie für die Vererbung im Objektmodell.  
  
 Weitere Informationen finden Sie unter [LINQ to SQL](../../../../framework/data/adonet/sql/linq/index.md).  
  
## <a name="linq-to-entities"></a>LINQ to Entities  
 Durch das [!INCLUDE[adonet_edm](~/includes/adonet-edm-md.md)] werden relationale Daten als Objekte in der .NET-Umgebung verfügbar gemacht. Dadurch wird die Objektebene zu einem optimalen Ziel für die [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)]-Unterstützung, die es Entwicklern ermöglicht, Abfragen an die Datenbank in der Sprache der Geschäftlogik zu formulieren. Dies wird als [!INCLUDE[linq_entities](~/includes/linq-entities-md.md)] bezeichnet. Weitere Informationen Sie unter [LINQ to Entities](../../../../framework/data/adonet/ef/language-reference/linq-to-entities.md).  
  
## <a name="see-also"></a>Siehe auch  
 [LINQ und ADO.NET](http://msdn.microsoft.com/library/bf0c8f93-3ff7-49f3-8aed-f2b7ac938dec)  
 [Language-Integrated Query (LINQ) (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/index.md)
