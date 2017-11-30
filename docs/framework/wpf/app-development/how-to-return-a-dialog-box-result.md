---
title: "Vorgehensweise: Zurückgeben einer Dialogfeldergebnis"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords: dialog boxes [WPF], returning results
ms.assetid: 4c5cf286-746b-4052-934d-d80cbf8acba3
caps.latest.revision: "4"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: d5a1b8cdc0544bfba3f708db40e8b9c593b45b35
ms.sourcegitcommit: c2e216692ef7576a213ae16af2377cd98d1a67fa
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/22/2017
---
# <a name="how-to-return-a-dialog-box-result"></a><span data-ttu-id="ad674-102">Vorgehensweise: Zurückgeben einer Dialogfeldergebnis</span><span class="sxs-lookup"><span data-stu-id="ad674-102">How to: Return a Dialog Box Result</span></span>
<span data-ttu-id="ad674-103">In diesem Beispiel wird gezeigt, wie das Dialogfeldergebnis für ein Fenster abrufen, die durch Aufrufen von <xref:System.Windows.Window.ShowDialog%2A>.</span><span class="sxs-lookup"><span data-stu-id="ad674-103">This example shows how to retrieve the dialog result for a window that is opened by calling <xref:System.Windows.Window.ShowDialog%2A>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="ad674-104">Beispiel</span><span class="sxs-lookup"><span data-stu-id="ad674-104">Example</span></span>  
 <span data-ttu-id="ad674-105">Bevor Sie ein Dialogfeld wird geschlossen, und seine <xref:System.Windows.Window.DialogResult%2A> Eigenschaft sollte festgelegt werden, mit einer <xref:System.Nullable%601> <xref:System.Boolean> , der angibt, wie der Benutzer das Dialogfeld geschlossen.</span><span class="sxs-lookup"><span data-stu-id="ad674-105">Before a dialog box closes, its <xref:System.Windows.Window.DialogResult%2A> property should be set with a <xref:System.Nullable%601><xref:System.Boolean> that indicates how the user closed the dialog box.</span></span> <span data-ttu-id="ad674-106">Dieser Wert wird zurückgegeben, indem <xref:System.Windows.Window.ShowDialog%2A> ermöglicht Clientcode, um zu bestimmen, wie das Dialogfeld geschlossen wurde und folglich wie das Ergebnis zu verarbeiten.</span><span class="sxs-lookup"><span data-stu-id="ad674-106">This value is returned by <xref:System.Windows.Window.ShowDialog%2A> to allow client code to determine how the dialog box was closed and, consequently, how to process the result.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="ad674-107"><xref:System.Windows.Window.DialogResult%2A>kann nur festgelegt werden, wenn ein Fenster, durch den Aufruf geöffnet wurde <xref:System.Windows.Window.ShowDialog%2A>.</span><span class="sxs-lookup"><span data-stu-id="ad674-107"><xref:System.Windows.Window.DialogResult%2A> can only be set if a window was opened by calling <xref:System.Windows.Window.ShowDialog%2A>.</span></span>  
  
 [!code-csharp[HOWTOWindowManagementSnippets#GetDialogResultCODE](../../../../samples/snippets/csharp/VS_Snippets_Wpf/HOWTOWindowManagementSnippets/CSharp/MainWindow.xaml.cs#getdialogresultcode)]
 [!code-vb[HOWTOWindowManagementSnippets#GetDialogResultCODE](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/HOWTOWindowManagementSnippets/visualbasic/mainwindow.xaml.vb#getdialogresultcode)]  
  
## <a name="net-framework-security"></a><span data-ttu-id="ad674-108">.NET Framework-Sicherheit</span><span class="sxs-lookup"><span data-stu-id="ad674-108">.NET Framework Security</span></span>  
 <span data-ttu-id="ad674-109">Aufrufen von <xref:System.Windows.Window.ShowDialog%2A> erfordert die Berechtigung, alle Fenster und Benutzereingabeereignisse uneingeschränkt verwendet.</span><span class="sxs-lookup"><span data-stu-id="ad674-109">Calling <xref:System.Windows.Window.ShowDialog%2A> requires permission to use all windows and user input events without restriction.</span></span>