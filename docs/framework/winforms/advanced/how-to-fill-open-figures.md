---
title: 'Gewusst wie: Ausfüllen offener Körper'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- open figures [Windows Forms], filling
- figures [Windows Forms], filling
ms.assetid: 5a36b0e4-f1f4-46c0-a85a-22ae98491950
ms.openlocfilehash: b7422ae2a4dc4d59fd337ab2294caa0d65057bae
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33521159"
---
# <a name="how-to-fill-open-figures"></a>Gewusst wie: Ausfüllen offener Körper
Sie können einen Pfad ausfüllen, durch das Übergeben einer <xref:System.Drawing.Drawing2D.GraphicsPath> -Objekt an die <xref:System.Drawing.Graphics.FillPath%2A> Methode. Die <xref:System.Drawing.Graphics.FillPath%2A> -Methode füllt den Pfad entsprechend der Füllmodus (alternate oder winding), die derzeit für den Pfad festlegen. Wenn der Pfad offener Körper verfügt, wird der Pfad gefüllt, als ob diese Zahlen geschlossen wurden. [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] Schließt eine Abbildung durch Zeichnen einer geraden Linie vom Endpunkt an seinem Ausgangspunkt.  
  
## <a name="example"></a>Beispiel  
 Das folgende Beispiel erstellt einen Pfad mit einer offenen Figur (einen Bogen) und eine geschlossene Form (Ellipse). Die <xref:System.Drawing.Graphics.FillPath%2A> -Methode füllt den Pfad entsprechend der Standardmodus für die Füllung, also <xref:System.Drawing.Drawing2D.FillMode.Alternate>.  
  
 Die folgende Abbildung zeigt die Ausgabe des Beispielcodes. Beachten Sie, dass der Pfad ist gefüllt (gemäß <xref:System.Drawing.Drawing2D.FillMode.Alternate>), als wäre der offene Körper durch eine gerade Linie vom Endpunkt an seinem Ausgangspunkt geschlossen wurden.  
  
 ![Offenen Pfad ausfüllen](../../../../docs/framework/winforms/advanced/media/fillopenpath.png "FillOpenPath")  
  
 [!code-csharp[System.Drawing.ConstructingDrawingPaths#11](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.ConstructingDrawingPaths/CS/Class1.cs#11)]
 [!code-vb[System.Drawing.ConstructingDrawingPaths#11](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.ConstructingDrawingPaths/VB/Class1.vb#11)]  
  
## <a name="compiling-the-code"></a>Kompilieren des Codes  
 Das obige Beispiel ist für die Verwendung in Windows Forms konzipiert und erfordert <xref:System.Windows.Forms.PaintEventArgs> `e`, einen Parameter des <xref:System.Windows.Forms.Control.Paint>-Ereignishandlers.  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.Drawing.Drawing2D.GraphicsPath>  
 [Grafikpfade in GDI+](../../../../docs/framework/winforms/advanced/graphics-paths-in-gdi.md)
