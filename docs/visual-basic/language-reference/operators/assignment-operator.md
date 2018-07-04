---
title: =-Operator (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.Assign
- vb.=
helpviewer_keywords:
- = operator [Visual Basic]
- = assignment statements [Visual Basic]
ms.assetid: 2dac2e49-86c8-42f8-80c1-458452fb5e29
ms.openlocfilehash: 55b3a8201940a6fec351327aaa88e4ac1ee9246a
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33603599"
---
# <a name="-operator-visual-basic"></a>=-Operator (Visual Basic)
Weist einen Wert einer Variable oder Eigenschaft zu.  
  
## <a name="syntax"></a>Syntax  
  
```  
variableorproperty = value  
```  
  
## <a name="parts"></a>Teile  
 `variableorproperty`  
 Jede schreibbare Variable oder eine Eigenschaft.  
  
 `value`  
 Ein Literal, eine Konstante oder ein Ausdruck.  
  
## <a name="remarks"></a>Hinweise  
 Das Element auf der linken Seite des Gleichheitszeichens (`=`) kann eine einfache Skalarvariable, eine Eigenschaft oder ein Element eines Arrays sein. Die Variable oder Eigenschaft darf nicht [ReadOnly](../../../visual-basic/language-reference/modifiers/readonly.md) sein. Der `=` -Operator weist den Wert auf der rechten Seite der Variablen oder Eigenschaft auf der linken Seite.  
  
> [!NOTE]
>  Die `=` Operator wird auch als Vergleichsoperator verwendet. Weitere Informationen finden Sie unter [Vergleichsoperatoren](../../../visual-basic/language-reference/operators/comparison-operators.md).  
  
## <a name="overloading"></a>Überladen  
 Die `=` Operator kann nur als relationalen Vergleichsoperator und nicht als Zuweisungsoperator überladen werden. Weitere Informationen finden Sie unter [Operatorprozeduren](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).  
  
## <a name="example"></a>Beispiel  
 Im folgende Beispiel wird veranschaulicht, wie der Zuweisungsoperator verwendet wird. Der Wert auf der rechten Seite wird der Variablen auf der linken Seite zugewiesen.  
  
 [!code-vb[VbVbalrOperators#9](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/assignment-operator_1.vb)]  
  
## <a name="see-also"></a>Siehe auch  
 [&=-Operator](../../../visual-basic/language-reference/operators/and-assignment-operator.md)  
 [* =-Operator](../../../visual-basic/language-reference/operators/multiplication-assignment-operator.md)  
 [+=-Operator](../../../visual-basic/language-reference/operators/addition-assignment-operator.md)  
 [Operator-=-Operator (Visual Basic)](../../../visual-basic/language-reference/operators/subtraction-assignment-operator.md)  
 [/ =-Operator (Visual Basic)](../../../visual-basic/language-reference/operators/floating-point-division-assignment-operator.md)  
 [\\=-Operator](../../../visual-basic/language-reference/operators/integer-division-assignment-operator.md)  
 [^=-Operator](../../../visual-basic/language-reference/operators/exponentiation-assignment-operator.md)  
 [Anweisungen](../../../visual-basic/programming-guide/language-features/statements.md)  
 [Vergleichsoperatoren](../../../visual-basic/language-reference/operators/comparison-operators.md)  
 [ReadOnly](../../../visual-basic/language-reference/modifiers/readonly.md)  
 [Lokaler Typrückschluss](../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md)
