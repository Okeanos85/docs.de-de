---
title: 'Gewusst wie: Ausfüllen einer Form mit einer Schraffur'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- patterns [Windows Forms], adding to shapes
- shapes [Windows Forms], filling with patterns
- brushes [Windows Forms], using hatch brushes
ms.assetid: 9c8300ff-187b-404f-af1f-ebd499f5b16f
ms.openlocfilehash: 5b6b5b61b83e5be05999099f2cc6b9e715ca35c7
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33521741"
---
# <a name="how-to-fill-a-shape-with-a-hatch-pattern"></a>Gewusst wie: Ausfüllen einer Form mit einer Schraffur
Eine Schraffur besteht aus zwei Farben: eine für den Hintergrund und eine für die Zeilen, die das Muster über dem Hintergrund bilden. Um eine geschlossene Form mit einer Schraffur zu füllen, verwenden Sie eine <xref:System.Drawing.Drawing2D.HatchBrush> Objekt. Im folgenden Beispiel wird veranschaulicht, wie eine Ellipse, die mit einer Schraffur füllen:  
  
## <a name="example"></a>Beispiel  
 Die <xref:System.Drawing.Drawing2D.HatchBrush.%23ctor%2A> Konstruktor hat drei Argumente: die Schraffurart, die Farbe der Schraffurlinie und die Farbe des Hintergrunds. Das Schraffurstilargument kann einen beliebigen Wert zwischen der <xref:System.Drawing.Drawing2D.HatchStyle> Enumeration. Es gibt mehr als 50 Elemente in der <xref:System.Drawing.Drawing2D.HatchStyle> -Enumeration; nur einige dieser Elemente sind in der folgenden Liste dargestellt:  
  
-   <xref:System.Drawing.Drawing2D.HatchStyle.Horizontal>  
  
-   <xref:System.Drawing.Drawing2D.HatchStyle.Vertical>  
  
-   <xref:System.Drawing.Drawing2D.HatchStyle.ForwardDiagonal>  
  
-   <xref:System.Drawing.Drawing2D.HatchStyle.BackwardDiagonal>  
  
-   <xref:System.Drawing.Drawing2D.HatchStyle.Cross>  
  
-   <xref:System.Drawing.Drawing2D.HatchStyle.DiagonalCross>  
  
 Die folgende Abbildung zeigt das ausgefüllte Ellipse.  
  
 ![Muster Schraffieren](../../../../docs/framework/winforms/advanced/media/hatch1.png "hatch1")  
  
 [!code-csharp[System.Drawing.UsingABrush#41](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.UsingABrush/CS/Class1.cs#41)]
 [!code-vb[System.Drawing.UsingABrush#41](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.UsingABrush/VB/Class1.vb#41)]  
  
## <a name="compiling-the-code"></a>Kompilieren des Codes  
 Das obige Beispiel ist für die Verwendung mit Windows Forms konzipiert und erfordert <xref:System.Windows.Forms.PaintEventArgs> `e`, einen Parameter von der <xref:System.Windows.Forms.Control.Paint> -Ereignishandler.  
  
## <a name="see-also"></a>Siehe auch  
 [Verwenden eines Pinsels zum Ausfüllen von Formen](../../../../docs/framework/winforms/advanced/using-a-brush-to-fill-shapes.md)
