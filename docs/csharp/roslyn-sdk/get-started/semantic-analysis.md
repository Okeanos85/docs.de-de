---
title: Erste Schritte mit der semantischen Analyse
description: "Dieses Tutorial bietet einen Überblick über die Arbeit mit semantischen Analysen mithilfe des .NET Compiler SDK."
author: billwagner
ms.author: wiwagn
ms.date: 02/06/2018
ms.topic: conceptual
ms.prod: .net
ms.devlang: devlang-csharp
ms.custom: mvc
ms.openlocfilehash: 04bd57dfd32a51bf5d7e3a573e34140b0feec90f
ms.sourcegitcommit: 3a96c706e4dbb4667bf3bf37edac9e1666646f93
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 02/27/2018
---
# <a name="get-started-with-semantic-analysis"></a><span data-ttu-id="bb912-103">Erste Schritte mit der semantischen Analyse</span><span class="sxs-lookup"><span data-stu-id="bb912-103">Get started with semantic analysis</span></span>

<span data-ttu-id="bb912-104">Bei diesem Tutorial wird davon ausgegangen, dass Sie mit der Syntax-API vertraut sind.</span><span class="sxs-lookup"><span data-stu-id="bb912-104">This tutorial assumes you're familiar with the Syntax API.</span></span> <span data-ttu-id="bb912-105">Der Artikel [Erste Schritte mit der Syntaxanalyse](syntax-analysis.md) bietet eine Einführung zu diesem Thema.</span><span class="sxs-lookup"><span data-stu-id="bb912-105">The [get started with syntax analysis](syntax-analysis.md) article provides sufficient introduction.</span></span>

<span data-ttu-id="bb912-106">Im vorliegenden Tutorial erkunden Sie die APIs für **Symbol** und **Bindung**.</span><span class="sxs-lookup"><span data-stu-id="bb912-106">In this tutorial, you explore the **Symbol** and **Binding APIs**.</span></span> <span data-ttu-id="bb912-107">Diese APIs bieten Informationen zur _semantischen Bedeutung_ eines Programms.</span><span class="sxs-lookup"><span data-stu-id="bb912-107">These APIs provide information about the _semantic meaning_ of a program.</span></span> <span data-ttu-id="bb912-108">Sie ermöglichen es Ihnen, Fragen zu den Typen zu stellen und zu beantworten, die durch ein Symbol in Ihrem Programm dargestellt werden.</span><span class="sxs-lookup"><span data-stu-id="bb912-108">They enable you to ask and answer questions about the types represented by any symbol in your program.</span></span>

## <a name="understanding-compilations-and-symbols"></a><span data-ttu-id="bb912-109">Grundlegendes zu Kompilierungen und Symbolen</span><span class="sxs-lookup"><span data-stu-id="bb912-109">Understanding Compilations and Symbols</span></span>

<span data-ttu-id="bb912-110">Wenn Sie eine Weile mit dem .NET Compiler SDK arbeiten, werden Ihnen die Unterschiede zwischen der Syntax-API und der Semantik-API immer vertrauter.</span><span class="sxs-lookup"><span data-stu-id="bb912-110">As you work more with the .NET Compiler SDK, you become familiar with the distinctions between Syntax API and the Semantic API.</span></span> <span data-ttu-id="bb912-111">Die **Syntax-API** ermöglicht es Ihnen, die _Struktur_ eines Programms zu untersuchen.</span><span class="sxs-lookup"><span data-stu-id="bb912-111">The **Syntax API** allows you to look at the _structure_ of a program.</span></span> <span data-ttu-id="bb912-112">In vielen Fällen benötigen Sie jedoch weitere Informationen zur Semantik bzw. _Bedeutung_ eines Programms.</span><span class="sxs-lookup"><span data-stu-id="bb912-112">However, often you want richer information about the semantics or _meaning_ of a program.</span></span> <span data-ttu-id="bb912-113">Sie können zwar eine einzelne, losgelöste Codedatei oder einen isolierten VB- oder C#-Codeausschnitt syntaktisch analysieren, aber es ist wenig sinnvoll, Fragen wie „Welchen Typ weist diese Variable auf?“ sozusagen im luftleeren Raum zu stellen.</span><span class="sxs-lookup"><span data-stu-id="bb912-113">While a loose code file or snippet of VB or C# code can be syntactically analyzed in isolation, it's not meaningful to ask questions such as "what's the type of this variable" in a vacuum.</span></span> <span data-ttu-id="bb912-114">Die Bedeutung eines Typnamens kann von Assemblyverweisen, Namespaceimporten oder anderen Codedateien abhängig sein.</span><span class="sxs-lookup"><span data-stu-id="bb912-114">The meaning of a type name may be dependent on assembly references, namespace imports, or other code files.</span></span> <span data-ttu-id="bb912-115">Diese Fragen werden mithilfe der **Semantik-API**, insbesondere der <xref:Microsoft.CodeAnalysis.Compilation?displayProperty=nameWithType>-Klasse, beantwortet.</span><span class="sxs-lookup"><span data-stu-id="bb912-115">Those questions are answered using the **Semantic API**, specifically the <xref:Microsoft.CodeAnalysis.Compilation?displayProperty=nameWithType> class.</span></span>

<span data-ttu-id="bb912-116">Eine Instanz von <xref:Microsoft.CodeAnalysis.Compilation> entspricht einem einzelnen Projekt aus Sicht des Compilers und repräsentiert alle Elemente, die zum Kompilieren eines Visual Basic- oder C#-Programms erforderlich sind.</span><span class="sxs-lookup"><span data-stu-id="bb912-116">An instance of <xref:Microsoft.CodeAnalysis.Compilation> is analogous to a single project as seen by the compiler and represents everything needed to compile a Visual Basic or C# program.</span></span> <span data-ttu-id="bb912-117">Die **Kompilierung** umfasst den Satz Quelldateien, die kompiliert werden sollen, sowie Assemblyverweise und Compileroptionen.</span><span class="sxs-lookup"><span data-stu-id="bb912-117">The **compilation** includes the set of source files to be compiled, assembly references, compiler options.</span></span> <span data-ttu-id="bb912-118">Sie können alle weiteren Informationen in diesem Kontext heranziehen, um die Bedeutung des Codes genau zu verstehen.</span><span class="sxs-lookup"><span data-stu-id="bb912-118">You can reason about the meaning of the code using all the other information in this context.</span></span> <span data-ttu-id="bb912-119">Eine <xref:Microsoft.CodeAnalysis.Compilation> ermöglicht es Ihnen, **Symbole** zu suchen: Entitäten wie z.B. Typen, Namespaces, Member und Variablen, auf die Namen und andere Ausdrücke verweisen.</span><span class="sxs-lookup"><span data-stu-id="bb912-119">A <xref:Microsoft.CodeAnalysis.Compilation> allows you to find **Symbols** - entities such as types, namespaces, members, and variables which names and other expressions refer to.</span></span> <span data-ttu-id="bb912-120">Der Prozess der Verknüpfung von Namen und Ausdrücken mit **Symbolen** wird als **Bindung** bezeichnet.</span><span class="sxs-lookup"><span data-stu-id="bb912-120">The process of associating names and expressions with **Symbols** is called **Binding**.</span></span>

<span data-ttu-id="bb912-121">Ebenso wie <xref:Microsoft.CodeAnalysis.SyntaxTree?displayProperty=nameWithType> ist <xref:Microsoft.CodeAnalysis.Compilation> eine abstrakte Klasse mit sprachspezifischen Ableitungen.</span><span class="sxs-lookup"><span data-stu-id="bb912-121">Like <xref:Microsoft.CodeAnalysis.SyntaxTree?displayProperty=nameWithType>, <xref:Microsoft.CodeAnalysis.Compilation> is an abstract class with language-specific derivatives.</span></span> <span data-ttu-id="bb912-122">Wenn Sie eine Instanz von „Compilation“ erstellen, müssen Sie eine Factorymethode in der Klasse <xref:Microsoft.CodeAnalysis.CSharp.CSharpCompilation?displayProperty=nameWithType> (oder <xref:Microsoft.CodeAnalysis.VisualBasic.VisualBasicCompilation?displayProperty=nameWithType>) aufrufen.</span><span class="sxs-lookup"><span data-stu-id="bb912-122">When creating an instance of Compilation, you must invoke a factory method on the <xref:Microsoft.CodeAnalysis.CSharp.CSharpCompilation?displayProperty=nameWithType> (or <xref:Microsoft.CodeAnalysis.VisualBasic.VisualBasicCompilation?displayProperty=nameWithType>) class.</span></span>

## <a name="querying-symbols"></a><span data-ttu-id="bb912-123">Abfragen von Symbolen</span><span class="sxs-lookup"><span data-stu-id="bb912-123">Querying symbols</span></span>

<span data-ttu-id="bb912-124">In diesem Tutorial betrachten wir noch einmal das Hello World-Programm.</span><span class="sxs-lookup"><span data-stu-id="bb912-124">In this tutorial, you look at the "Hello World" program again.</span></span> <span data-ttu-id="bb912-125">Diesmal fragen Sie die Symbole im Programm ab, um zu verstehen, welche Typen durch diese Symbole repräsentiert werden.</span><span class="sxs-lookup"><span data-stu-id="bb912-125">This time, you query the symbols in the program to understand what types those symbols represent.</span></span> <span data-ttu-id="bb912-126">Sie fragen die Typen in einem Namespace ab und lernen, wie Sie die verfügbaren Methoden in einem Typ finden.</span><span class="sxs-lookup"><span data-stu-id="bb912-126">You query for the types in a namespace, and learn to find the methods available on a type.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="bb912-127">Für die folgenden Beispiele muss das **.NET Compiler SDK** als Teil von Visual Studio 2017 installiert sein.</span><span class="sxs-lookup"><span data-stu-id="bb912-127">The following samples require the **.NET Compiler SDK** installed as part of Visual Studio 2017.</span></span> <span data-ttu-id="bb912-128">Das .NET Compiler SDK wird in der Workload **Visual Studio-Erweiterungsentwicklung** als letzte optionale Komponente aufgeführt.</span><span class="sxs-lookup"><span data-stu-id="bb912-128">You can find the .NET Compiler SDK as the last optional component listed under the **Visual Studio extension development** workload.</span></span> <span data-ttu-id="bb912-129">Ohne diese Komponente lassen sich die Vorlagen nicht installieren.</span><span class="sxs-lookup"><span data-stu-id="bb912-129">The templates aren't installed without this component.</span></span>

<span data-ttu-id="bb912-130">Den fertig gestellten Code für dieses Beispiel finden Sie in [unserem GitHub-Beispielrepository](https://github.com/dotnet/samples/csharp/roslyn-sdk/SemanticQuickStart).</span><span class="sxs-lookup"><span data-stu-id="bb912-130">You can see the finished code for this sample in [our GitHub samples repository](https://github.com/dotnet/samples/csharp/roslyn-sdk/SemanticQuickStart).</span></span>

> [!NOTE]
> <span data-ttu-id="bb912-131">Die Syntaxstrukturtypen verwenden Vererbung, um die verschiedenen Syntaxelemente zu beschreiben, die an verschiedenen Positionen im Programm gültig sind.</span><span class="sxs-lookup"><span data-stu-id="bb912-131">The Syntax Tree types use inheritance to describe the different syntax elements that are valid at different locations in the program.</span></span> <span data-ttu-id="bb912-132">Bei der Verwendung dieser APIs müssen häufig Eigenschaften oder Sammlungsmember in bestimmte abgeleitete Typen umgewandelt werden.</span><span class="sxs-lookup"><span data-stu-id="bb912-132">Using these APIs often means casting properties or collection members to specific derived types.</span></span> <span data-ttu-id="bb912-133">In den folgenden Beispielen sind die Zuweisung und die Umwandlung separate Anweisungen, bei denen explizit typisierte Variablen verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="bb912-133">In the following examples, the assignment and the casts are separate statements, using explicitly typed variables.</span></span> <span data-ttu-id="bb912-134">Sie können den Code lesen, um die Rückgabetypen der API und den Laufzeittyp der zurückgegebenen Objekte zu sehen.</span><span class="sxs-lookup"><span data-stu-id="bb912-134">You can read the code to see the return types of the API and the runtime type of the objects returned.</span></span> <span data-ttu-id="bb912-135">In der Praxis ist es eher üblich, implizit typisierte Variablen zu verwenden und die Typen der zu untersuchenden Objekte mithilfe von API-Namen zu beschreiben.</span><span class="sxs-lookup"><span data-stu-id="bb912-135">In practice, it's more common to use implicitly typed variables and rely on API names to describe the type of objects being examined.</span></span>

<span data-ttu-id="bb912-136">Erstellen Sie ein neues **Stand-Alone Code Analysis Tool**-Projekt für C#:</span><span class="sxs-lookup"><span data-stu-id="bb912-136">Create a new C# **Stand-Alone Code Analysis Tool** project:</span></span>

* <span data-ttu-id="bb912-137">Wählen Sie in Visual Studio **Datei** > **Neu** > **Projekt** aus, um das Dialogfeld „Neues Projekt“ anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="bb912-137">In Visual Studio, choose **File** > **New** > **Project** to display the New Project dialog.</span></span>
* <span data-ttu-id="bb912-138">Wählen Sie unter **Visual C#** > **Erweiterbarkeit** die Option **Stand-Alone Code Analysis Tool** aus.</span><span class="sxs-lookup"><span data-stu-id="bb912-138">Under **Visual C#** > **Extensibility**, choose **Stand-Alone Code Analysis Tool**.</span></span>
* <span data-ttu-id="bb912-139">Nennen Sie Ihr Projekt **SemanticQuickStart**, und klicken Sie auf „OK“.</span><span class="sxs-lookup"><span data-stu-id="bb912-139">Name your project "**SemanticQuickStart**" and click OK.</span></span>

<span data-ttu-id="bb912-140">Sie werden das einfache Hello World!-</span><span class="sxs-lookup"><span data-stu-id="bb912-140">You're going to analyze the basic "Hello World!"</span></span> <span data-ttu-id="bb912-141">Programm analysieren, das weiter oben in diesem Artikel gezeigt wurde.</span><span class="sxs-lookup"><span data-stu-id="bb912-141">program shown earlier.</span></span>
<span data-ttu-id="bb912-142">Fügen Sie den Text für das Hello World-Programm als Konstante in Ihre `Program`-Klasse ein:</span><span class="sxs-lookup"><span data-stu-id="bb912-142">Add the text for the Hello World program as a constant in your `Program` class:</span></span>

[!code-csharp[Declare the program test](../../../../samples/csharp/roslyn-sdk/SemanticQuickStart/SemanticQuickStart/Program.cs#1 "Declare a constant string for the program text to analyze")]

<span data-ttu-id="bb912-143">Anschließend fügen Sie den folgenden Code hinzu, um die Syntaxstruktur für den Codetext in der `programText`-Konstante zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="bb912-143">Next, add the following code to build the syntax tree for the code text in the `programText` constant.</span></span>  <span data-ttu-id="bb912-144">Fügen Sie Ihrer `Main`-Methode die folgende Zeile hinzu:</span><span class="sxs-lookup"><span data-stu-id="bb912-144">Add the following line to your `Main` method:</span></span>

[!code-csharp[Create the tree](../../../../samples/csharp/roslyn-sdk/SemanticQuickStart/SemanticQuickStart/Program.cs#2 "Create the syntax tree")]

<span data-ttu-id="bb912-145">Anschließend erstellen Sie aus der bereits erstellten Struktur eine <xref:Microsoft.CodeAnalysis.CSharp.CSharpCompilation>.</span><span class="sxs-lookup"><span data-stu-id="bb912-145">Next, build a <xref:Microsoft.CodeAnalysis.CSharp.CSharpCompilation> from the tree you already created.</span></span> <span data-ttu-id="bb912-146">Das Hello World-Beispiel basiert auf den Typen <xref:System.String> und <xref:System.Console>.</span><span class="sxs-lookup"><span data-stu-id="bb912-146">The "Hello World" sample relies on the <xref:System.String> and <xref:System.Console> types.</span></span> <span data-ttu-id="bb912-147">Sie müssen auf die Assembly verweisen, die diese beiden Typen in Ihrer Kompilierung deklariert.</span><span class="sxs-lookup"><span data-stu-id="bb912-147">You need to reference the assembly that declares those two types in your compilation.</span></span> <span data-ttu-id="bb912-148">Fügen Sie Ihrer `Main`-Methode folgende Zeile hinzu, um eine Kompilierung Ihrer Syntaxstruktur einschließlich des Verweises auf die entsprechende Assembly zu erstellen:</span><span class="sxs-lookup"><span data-stu-id="bb912-148">Add the following line to your `Main` method to create a compilation of your syntax tree, including the reference to the appropriate assembly:</span></span>

[!code-csharp[Create the compilation](../../../../samples/csharp/roslyn-sdk/SemanticQuickStart/SemanticQuickStart/Program.cs#3 "Create the compilation for the semantic model")]

<span data-ttu-id="bb912-149">Die <xref:Microsoft.CodeAnalysis.CSharp.CSharpCompilation.AddReferences%2A?displayProperty=nameWithType>-Methode fügt Verweise zur Kompilierung hinzu.</span><span class="sxs-lookup"><span data-stu-id="bb912-149">The <xref:Microsoft.CodeAnalysis.CSharp.CSharpCompilation.AddReferences%2A?displayProperty=nameWithType> method adds references to the compilation.</span></span> <span data-ttu-id="bb912-150">Die <xref:Microsoft.CodeAnalysis.MetadataReference.CreateFromFile(System.String,Microsoft.CodeAnalysis.MetadataReferenceProperties,Microsoft.CodeAnalysis.DocumentationProvider)>-Methode lädt eine Assembly als Verweis.</span><span class="sxs-lookup"><span data-stu-id="bb912-150">The <xref:Microsoft.CodeAnalysis.MetadataReference.CreateFromFile(System.String,Microsoft.CodeAnalysis.MetadataReferenceProperties,Microsoft.CodeAnalysis.DocumentationProvider)> method loads an assembly as a reference.</span></span> 

## <a name="querying-the-semantic-model"></a><span data-ttu-id="bb912-151">Abfragen des semantischen Modells</span><span class="sxs-lookup"><span data-stu-id="bb912-151">Querying the semantic model</span></span>

<span data-ttu-id="bb912-152">Sobald Sie über eine <xref:Microsoft.CodeAnalysis.Compilation> verfügen, können Sie diese nach einem <xref:Microsoft.CodeAnalysis.SemanticModel> für jede <xref:Microsoft.CodeAnalysis.SyntaxTree> in dieser <xref:Microsoft.CodeAnalysis.Compilation> abfragen.</span><span class="sxs-lookup"><span data-stu-id="bb912-152">Once you have a <xref:Microsoft.CodeAnalysis.Compilation> you can ask it for a <xref:Microsoft.CodeAnalysis.SemanticModel> for any <xref:Microsoft.CodeAnalysis.SyntaxTree> contained in that <xref:Microsoft.CodeAnalysis.Compilation>.</span></span> <span data-ttu-id="bb912-153">Sie können sich das Semantikmodell als die Quelle aller Informationen vorstellen, die Sie normalerweise aus IntelliSense erhalten.</span><span class="sxs-lookup"><span data-stu-id="bb912-153">You can think of the semantic model as the source for all the information would normally get from intellisense.</span></span> <span data-ttu-id="bb912-154">Eine <xref:Microsoft.CodeAnalysis.SemanticModel> kann Fragen wie diese beantworten: „Welche Namen befinden sich an dieser Stelle im Gültigkeitsbereich?“,</span><span class="sxs-lookup"><span data-stu-id="bb912-154">A <xref:Microsoft.CodeAnalysis.SemanticModel> can answer questions like "What names are in scope at this location?"</span></span> <span data-ttu-id="bb912-155">„Auf welche Member kann diese Methode zugreifen?“,</span><span class="sxs-lookup"><span data-stu-id="bb912-155">"What members are accessible from this method?"</span></span> <span data-ttu-id="bb912-156">„Welche Variablen werden in diesem Textblock verwendet?“</span><span class="sxs-lookup"><span data-stu-id="bb912-156">"What variables are used in this block of text?"</span></span> <span data-ttu-id="bb912-157">und „Worauf bezieht sich dieser Name bzw. Ausdruck?“.</span><span class="sxs-lookup"><span data-stu-id="bb912-157">and "What does this name/expression refer to?"</span></span> <span data-ttu-id="bb912-158">Fügen Sie diese Anweisung hinzu, um das semantische Modell zu erstellen:</span><span class="sxs-lookup"><span data-stu-id="bb912-158">Add this statement to create the semantic model:</span></span>

[!code-csharp[Create the semantic model](../../../../samples/csharp/roslyn-sdk/SemanticQuickStart/SemanticQuickStart/Program.cs#4 "Create the semantic model")]

## <a name="binding-a-name"></a><span data-ttu-id="bb912-159">Binden eines Namens</span><span class="sxs-lookup"><span data-stu-id="bb912-159">Binding a name</span></span>

<span data-ttu-id="bb912-160">Die <xref:Microsoft.CodeAnalysis.Compilation> erstellt das <xref:Microsoft.CodeAnalysis.SemanticModel> aus der <xref:Microsoft.CodeAnalysis.SyntaxTree>.</span><span class="sxs-lookup"><span data-stu-id="bb912-160">The <xref:Microsoft.CodeAnalysis.Compilation> creates the  <xref:Microsoft.CodeAnalysis.SemanticModel> from the <xref:Microsoft.CodeAnalysis.SyntaxTree>.</span></span> <span data-ttu-id="bb912-161">Nach dem Erstellen des Modells können Sie es abfragen, um die erste `using`-Direktive zu suchen und die Symbolinformationen für den `System`-Namespace abzurufen.</span><span class="sxs-lookup"><span data-stu-id="bb912-161">After creating the model, you can query it to find the first `using` directive, and retrieve the symbol information for the `System` namespace.</span></span> <span data-ttu-id="bb912-162">Fügen Sie die folgenden beiden Zeilen zu Ihrer `Main`-Methode hinzu, um das Semantikmodell zu erstellen und das Symbol für die erste using-Anweisung abzurufen:</span><span class="sxs-lookup"><span data-stu-id="bb912-162">Add these two lines to your `Main` method to create the semantic model and retrieve the symbol for the first using statement:</span></span>

[!code-csharp[Find the namespace symbol for the first using](../../../../samples/csharp/roslyn-sdk/SemanticQuickStart/SemanticQuickStart/Program.cs#5 "Find the namespace symbol for the first using")]

<span data-ttu-id="bb912-163">Der oben gezeigte Code veranschaulicht, wie Sie ein <xref:Microsoft.CodeAnalysis.SemanticModel>-Objekt für Ihre HelloWorld-<xref:Microsoft.CodeAnalysis.SyntaxTree> abrufen.</span><span class="sxs-lookup"><span data-stu-id="bb912-163">The preceding code shows how to obtain a <xref:Microsoft.CodeAnalysis.SemanticModel> object for your HelloWorld <xref:Microsoft.CodeAnalysis.SyntaxTree>.</span></span> <span data-ttu-id="bb912-164">Nachdem das Modell abgerufen wurde, wird der Name in der ersten `using`-Direktive gebunden, um eine <xref:Microsoft.CodeAnalysis.SymbolInfo?displayProperty=nameWithType> für den `System`-Namespace abzurufen.</span><span class="sxs-lookup"><span data-stu-id="bb912-164">Once the model is obtained, the name in the first `using` directive is bound to retrieve a <xref:Microsoft.CodeAnalysis.SymbolInfo?displayProperty=nameWithType> for the `System` namespace.</span></span> <span data-ttu-id="bb912-165">Dieser Code verdeutlicht auch, dass Sie das **Syntaxmodell** verwenden, um die Struktur des Codes zu ermitteln. Das **Semantikmodell** verwenden Sie, um die Bedeutung des Codes zu verstehen.</span><span class="sxs-lookup"><span data-stu-id="bb912-165">The preceding code also illustrates that you use the **syntax model** to find the structure of the code; you use the **semantic model** to understand its meaning.</span></span> <span data-ttu-id="bb912-166">Das **Syntaxmodell** sucht die Zeichenfolge `System` in der using-Anweisung.</span><span class="sxs-lookup"><span data-stu-id="bb912-166">The **syntax model** finds the string `System` in the using statement.</span></span> <span data-ttu-id="bb912-167">Das **Semantikmodell** verfügt über alle Informationen zu den im `System`-Namespace definierten Typen.</span><span class="sxs-lookup"><span data-stu-id="bb912-167">The **semantic model** has all the information about the types defined in the `System` namespace.</span></span>

<span data-ttu-id="bb912-168">Aus dem <xref:Microsoft.CodeAnalysis.SymbolInfo>-Objekt können Sie mithilfe der <xref:Microsoft.CodeAnalysis.SymbolInfo.Symbol?displayProperty=nameWithType>-Eigenschaft das <xref:Microsoft.CodeAnalysis.ISymbol?displayProperty=nameWithType> abrufen.</span><span class="sxs-lookup"><span data-stu-id="bb912-168">From the <xref:Microsoft.CodeAnalysis.SymbolInfo> object you can obtain the <xref:Microsoft.CodeAnalysis.ISymbol?displayProperty=nameWithType> using the <xref:Microsoft.CodeAnalysis.SymbolInfo.Symbol?displayProperty=nameWithType> property.</span></span> <span data-ttu-id="bb912-169">Diese Eigenschaft gibt das Symbol zurück, auf das dieser Ausdruck verweist.</span><span class="sxs-lookup"><span data-stu-id="bb912-169">This property returns the symbol this expression refers to.</span></span> <span data-ttu-id="bb912-170">Bei Ausdrücken, die auf nichts verweisen (wie z.B. numerische Literale), lautet diese Eigenschaft `null`.</span><span class="sxs-lookup"><span data-stu-id="bb912-170">For expressions that don't refer to anything (such as numeric literals) this property is `null`.</span></span> <span data-ttu-id="bb912-171">Wenn <xref:Microsoft.CodeAnalysis.SymbolInfo.Symbol?displayProperty=nameWithType> nicht null ist, bezeichnet <xref:Microsoft.CodeAnalysis.ISymbol.Kind?displayProperty=nameWithType> den Typ des Symbols.</span><span class="sxs-lookup"><span data-stu-id="bb912-171">When the <xref:Microsoft.CodeAnalysis.SymbolInfo.Symbol?displayProperty=nameWithType> is not null, the <xref:Microsoft.CodeAnalysis.ISymbol.Kind?displayProperty=nameWithType> denotes the type of the symbol.</span></span> <span data-ttu-id="bb912-172">In diesem Beispiel ist die <xref:Microsoft.CodeAnalysis.ISymbol.Kind?displayProperty=nameWithType>-Eigenschaft ein <xref:Microsoft.CodeAnalysis.SymbolKind.Namespace?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="bb912-172">In this example, the <xref:Microsoft.CodeAnalysis.ISymbol.Kind?displayProperty=nameWithType> property is a <xref:Microsoft.CodeAnalysis.SymbolKind.Namespace?displayProperty=nameWithType>.</span></span> <span data-ttu-id="bb912-173">Fügen Sie der `Main`-Methode den folgenden Code hinzu.</span><span class="sxs-lookup"><span data-stu-id="bb912-173">Add the following code to your `Main` method.</span></span> <span data-ttu-id="bb912-174">Der Code ruft das Symbol für den `System`-Namespace ab und zeigt alle untergeordneten Namespaces an, die im `System`-Namespace deklariert sind:</span><span class="sxs-lookup"><span data-stu-id="bb912-174">It retrieves the symbol for the `System` namespace and then displays all the child namespaces declared in the `System` namespace:</span></span>

[!code-csharp[Display all the child namespaces](../../../../samples/csharp/roslyn-sdk/SemanticQuickStart/SemanticQuickStart/Program.cs#6 "Display all the child namespaces from this compilation")]

<span data-ttu-id="bb912-175">Führen Sie das Programm aus. Folgende Ausgabe sollte angezeigt werden:</span><span class="sxs-lookup"><span data-stu-id="bb912-175">Run the program and you should see the following output:</span></span>

```
Collections
Configuration
Deployment
Diagnostics
Globalization
IO
Reflection
Resources
Runtime
Security
StubHelpers
Text
Threading
Press any key to continue . . .
```

> [!NOTE]
> <span data-ttu-id="bb912-176">Die Ausgabe umfasst nicht jeden Namespace, der ein untergeordneter Namespace des `System`-Namespace ist.</span><span class="sxs-lookup"><span data-stu-id="bb912-176">The output does not include every namespace that is a child namespace of the `System` namespace.</span></span> <span data-ttu-id="bb912-177">Sie zeigt jeden Namespace an, der in dieser Kompilierung vorhanden ist. Diese verweist nur auf die Assembly, in der `System.String` deklariert ist.</span><span class="sxs-lookup"><span data-stu-id="bb912-177">It displays every namespace that is present in this compilation, which only references the assembly where `System.String` is declared.</span></span> <span data-ttu-id="bb912-178">Namespaces, die in anderen Assemblys deklariert wurden, sind dieser Kompilierung unbekannt.</span><span class="sxs-lookup"><span data-stu-id="bb912-178">Any namespaces declared in other assemblies are not known to this compilation</span></span>

### <a name="binding-an-expression"></a><span data-ttu-id="bb912-179">Binden eines Ausdrucks</span><span class="sxs-lookup"><span data-stu-id="bb912-179">Binding an expression</span></span>

<span data-ttu-id="bb912-180">Der oben gezeigte Code veranschaulicht, wie Sie ein Symbol suchen, indem Sie es an einen Namen binden.</span><span class="sxs-lookup"><span data-stu-id="bb912-180">The preceding code shows how to find a symbol by binding to a name.</span></span> <span data-ttu-id="bb912-181">Es gibt weitere Ausdrücke in einem C#-Programm, die gebunden werden können, aber keine Namen sind.</span><span class="sxs-lookup"><span data-stu-id="bb912-181">There are other expressions in a C# program that can be bound that aren't names.</span></span> <span data-ttu-id="bb912-182">Um diese Funktion zu demonstrieren, sehen wir uns die Bindung an ein einfaches Zeichenfolgenliteral an.</span><span class="sxs-lookup"><span data-stu-id="bb912-182">To demonstrate this capability, let's access the binding to a simple string literal.</span></span>

<span data-ttu-id="bb912-183">Das Hello World-Programm enthält eine <xref:Microsoft.CodeAnalysis.CSharp.Syntax.LiteralExpressionSyntax?displayProperty=nameWithType>: die Hello, World!-</span><span class="sxs-lookup"><span data-stu-id="bb912-183">The "Hello World" program contains a <xref:Microsoft.CodeAnalysis.CSharp.Syntax.LiteralExpressionSyntax?displayProperty=nameWithType>, the "Hello, World!"</span></span> <span data-ttu-id="bb912-184">Zeichenfolge, die in der Konsole angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="bb912-184">string displayed to the console.</span></span>

<span data-ttu-id="bb912-185">Sie finden die Hello, World!-</span><span class="sxs-lookup"><span data-stu-id="bb912-185">You find the "Hello, World!"</span></span> <span data-ttu-id="bb912-186">Zeichenfolge, indem Sie das einzelne Zeichenfolgenliteral im Programm suchen.</span><span class="sxs-lookup"><span data-stu-id="bb912-186">string by locating the single string literal in the program.</span></span> <span data-ttu-id="bb912-187">Wenn Sie den Syntaxknoten gefunden haben, rufen Sie die Typinformationen für diesen Knoten aus dem Semantikmodell ab.</span><span class="sxs-lookup"><span data-stu-id="bb912-187">Then, once you've located the syntax node, get the type info for that node from the semantic model.</span></span> <span data-ttu-id="bb912-188">Fügen Sie der `Main`-Methode den folgenden Code hinzu:</span><span class="sxs-lookup"><span data-stu-id="bb912-188">Add the following code to your `Main` method:</span></span>

[!code-csharp[Find the namespace symbol for the only using](../../../../samples/csharp/roslyn-sdk/SemanticQuickStart/SemanticQuickStart/Program.cs#7 "Find the namespace symbol for the only using")]

<span data-ttu-id="bb912-189">Die <xref:Microsoft.CodeAnalysis.TypeInfo?displayProperty=nameWithType>-Struktur enthält eine <xref:Microsoft.CodeAnalysis.TypeInfo.Type?displayProperty=nameWithType>-Eigenschaft, die Zugriff auf die semantischen Informationen zum Typ des Literals erlaubt.</span><span class="sxs-lookup"><span data-stu-id="bb912-189">The <xref:Microsoft.CodeAnalysis.TypeInfo?displayProperty=nameWithType> struct includes a <xref:Microsoft.CodeAnalysis.TypeInfo.Type?displayProperty=nameWithType> property that enables access to the semantic information about the type of the literal.</span></span> <span data-ttu-id="bb912-190">In diesem Beispiel handelt es sich um den Typ `string`.</span><span class="sxs-lookup"><span data-stu-id="bb912-190">In this example, that's the `string` type.</span></span> <span data-ttu-id="bb912-191">Fügen Sie eine Deklaration hinzu, die diese Eigenschaft einer lokalen Variable zuweist:</span><span class="sxs-lookup"><span data-stu-id="bb912-191">Add a declaration that assigns this property to a local variable:</span></span>

[!code-csharp[Find the semantic information about the string type](../../../../samples/csharp/roslyn-sdk/SemanticQuickStart/SemanticQuickStart/Program.cs#8 "Use the string literal to access the semantic information in the string type.")]

<span data-ttu-id="bb912-192">Zum Abschluss dieses Tutorials erstellen wir eine LINQ-Abfrage, die eine Sequenz aller öffentlichen Methoden erstellt, die im `string`-Typ deklariert sind und eine `string` zurückgeben.</span><span class="sxs-lookup"><span data-stu-id="bb912-192">To finish this tutorial, let's build a LINQ query that creates a sequence of all the public methods declared on the `string` type that return a `string`.</span></span> <span data-ttu-id="bb912-193">Diese Abfrage wird ziemlich komplex – wir bauen sie daher Zeile für Zeile auf und rekonstruieren sie dann als Einzelabfrage.</span><span class="sxs-lookup"><span data-stu-id="bb912-193">This query gets complex, so let's build it line by line, then reconstruct it as a single query.</span></span> <span data-ttu-id="bb912-194">Die Quelle dieser Abfrage ist die Sequenz aller Member, die im `string`-Typ deklariert sind:</span><span class="sxs-lookup"><span data-stu-id="bb912-194">The source for this query is the sequence of all members declared on the `string` type:</span></span>

[!code-csharp[Access the sequence of members on the string type](../../../../samples/csharp/roslyn-sdk/SemanticQuickStart/SemanticQuickStart/Program.cs#9 "Access the sequence of members on the string type.")]

<span data-ttu-id="bb912-195">Diese Quellsequenz enthält alle Member, einschließlich Eigenschaften und Feldern. Filtern Sie die Sequenz daher mit der <xref:System.Collections.Immutable.ImmutableArray%601.OfType%2A?displayProperty=nameWithType>-Methode, um die Elemente zu finden, bei denen es sich um <xref:Microsoft.CodeAnalysis.IMethodSymbol?diplayProperty=nameWithType>-Objekte handelt:</span><span class="sxs-lookup"><span data-stu-id="bb912-195">That source sequence conatins all members, including properties and fields, so filter it using the <xref:System.Collections.Immutable.ImmutableArray%601.OfType%2A?displayProperty=nameWithType> method to find elements that are <xref:Microsoft.CodeAnalysis.IMethodSymbol?diplayProperty=nameWithType> objects:</span></span>

[!code-csharp[Filter the sequence to only methods](../../../../samples/csharp/roslyn-sdk/SemanticQuickStart/SemanticQuickStart/Program.cs#10 "Find the subset of the collection that is the methods.")]

<span data-ttu-id="bb912-196">Danach fügen Sie einen weiteren Filter hinzu, um nur die Methoden zurückzugeben, die öffentlich sind und eine `string` zurückgeben:</span><span class="sxs-lookup"><span data-stu-id="bb912-196">Next, add another filter to return only those methods that are public and return a `string`:</span></span>

[!code-csharp[Filter on return type and accessibility](../../../../samples/csharp/roslyn-sdk/SemanticQuickStart/SemanticQuickStart/Program.cs#11 "Find only the public methods that return a string.")]

<span data-ttu-id="bb912-197">Wählen Sie nur die name-Eigenschaft und nur eindeutige Namen aus, indem Sie alle Überladungen entfernen:</span><span class="sxs-lookup"><span data-stu-id="bb912-197">Select only the name property, and only distinct names by removing any overloads:</span></span>

[!code-csharp[find the distinct names.](../../../../samples/csharp/roslyn-sdk/SemanticQuickStart/SemanticQuickStart/Program.cs#12 "Use the string literal to access the semantic information in the string type.")]

<span data-ttu-id="bb912-198">Sie können auch mithilfe der LINQ-Abfragesyntax die vollständige Abfrage erstellen und dann alle Methodennamen in der Konsole anzeigen:</span><span class="sxs-lookup"><span data-stu-id="bb912-198">You can also build the full query using the LINQ query syntax, and then display all the method names in  the console:</span></span>

[!code-csharp[build and display the results of this query.](../../../../samples/csharp/roslyn-sdk/SemanticQuickStart/SemanticQuickStart/Program.cs#12 "Build and display the results of the query.")]

<span data-ttu-id="bb912-199">Kompilieren Sie das Programm, und führen Sie es aus.</span><span class="sxs-lookup"><span data-stu-id="bb912-199">Build and run the program.</span></span> <span data-ttu-id="bb912-200">Die folgende Ausgabe wird angezeigt:</span><span class="sxs-lookup"><span data-stu-id="bb912-200">You should see the following output:</span></span>

```
Join
Substring
Trim
TrimStart
TrimEnd
Normalize
PadLeft
PadRight
ToLower
ToLowerInvariant
ToUpper
ToUpperInvariant
ToString
Insert
Replace
Remove
Format
Copy
Concat
Intern
IsInterned
Press any key to continue . . .
```
<span data-ttu-id="bb912-201">Sie haben die Semantik-API verwendet, um Informationen zu den Symbolen zu finden und anzuzeigen, die zu diesem Programm gehören.</span><span class="sxs-lookup"><span data-stu-id="bb912-201">You've used the Semantic API to find and display information about the symbols that are part of this program.</span></span>