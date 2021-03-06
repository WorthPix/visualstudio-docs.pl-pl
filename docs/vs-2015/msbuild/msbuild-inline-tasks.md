---
title: Zadania wbudowane programu MSBuild | Dokumentacja firmy Microsoft
ms.custom: ''
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- MSBuild, tasks
ms.assetid: e72e6506-4a11-4edf-ae8d-cfb5a3b9d8a0
caps.latest.revision: 23
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: b706aa4de24152a7cf656b2cec9aee64f36d7773
ms.sourcegitcommit: 9ceaf69568d61023868ced59108ae4dd46f720ab
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/12/2018
ms.locfileid: "49223460"
---
# <a name="msbuild-inline-tasks"></a>Zadania wbudowane programu MSBuild
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

  
Zadania programu MSBuild są zwykle tworzone przez skompilowanie klasy, która implementuje <xref:Microsoft.Build.Framework.ITask> interfejsu. Aby uzyskać więcej informacji, zobacz [zadania](../msbuild/msbuild-tasks.md).  
  
 Począwszy od .NET Framework w wersji 4, można utworzyć zadania wbudowane w pliku projektu. Nie trzeba utworzyć osobny zestaw do obsługi zadań. Dzięki temu łatwiej do śledzenia kodu źródłowego i łatwiejsze do wdrożenia zadania. Kod źródłowy jest zintegrowany skrypt.  
  
## <a name="the-structure-of-an-inline-task"></a>Struktura zadania wbudowanego  
 Zadania wbudowanego jest zawarty w [UsingTask](../msbuild/usingtask-element-msbuild.md) elementu. Zadania wbudowane i `UsingTask` zawierający go zwykle są zawarte w pliku .targets i zaimportować do innych plików projektów, zgodnie z potrzebami. Poniżej przedstawiono podstawowe wbudowane zadania. Należy zauważyć, że nic nie robi.  
  
```  
<Project ToolsVersion="12.0" xmlns="http://schemas.microsoft.com/developer/msbuild/2003">  
  <!-- This simple inline task does nothing. -->  
  <UsingTask  
    TaskName="DoNothing"  
    TaskFactory="CodeTaskFactory"  
    AssemblyFile="$(MSBuildToolsPath)\Microsoft.Build.Tasks.v12.0.dll" >  
    <ParameterGroup />  
    <Task>  
      <Reference Include="" />  
      <Using Namespace="" />  
      <Code Type="Fragment" Language="cs">  
      </Code>  
    </Task>  
  </UsingTask>  
</Project>  
```  
  
 `UsingTask` Element w przykładzie ma trzy atrybuty, które opisują zadania i wbudowane fabryki zadań, który kompiluje go.  
  
-   `TaskName` Nazwy atrybutów, zadania, w tym przypadku `DoNothing`.  
  
-   `TaskFactory` Atrybutu nazwy klasy, która implementuje fabryki zadań w tekście.  
  
-   `AssemblyFile` Atrybutu zapewnia lokalizacji fabryki zadań w tekście. Alternatywnie, można użyć `AssemblyName` atrybutu, aby określić w pełni kwalifikowana nazwa klasy fabryki wbudowanych zadań, która znajduje się w globalnej pamięci podręcznej zestawów (GAC).  
  
 Pozostałe elementy `DoNothing` zadania są puste, znajdują się w celu zilustrowania kolejności i struktura zadania wbudowanego. Bardziej niezawodna przykład został przedstawiony w dalszej części tego tematu.  
  
-   `ParameterGroup` Element jest opcjonalne. Jeśli zostanie określony, deklaruje parametrów zadania. Aby uzyskać więcej informacji na temat parametrów wejściowych i wyjściowych zobacz "Danych wejściowych i danych wyjściowych parametry" w dalszej części tego tematu.  
  
-   `Task` Element opisuje i zawiera kod źródłowy zadania.  
  
-   `Reference` Element określa odwołania do zestawów .NET, które są używane w kodzie. Jest to równoważne do dodawania odwołania do projektu w programie Visual Studio. `Include` Atrybut ścieżka przywoływanego zestawu.  
  
-   `Using` Element zawiera przestrzenie nazw, które chcesz uzyskać dostęp. Przypomina to `Using` instrukcji w języku Visual C#. `Namespace` Atrybut określa przestrzeń nazw do uwzględnienia.  
  
 `Reference` i `Using` elementy są one niezależne od języka. Zadania wbudowane można pisać w jednym z obsługiwanych języków .NET CodeDom, na przykład Visual Basic lub Visual C#.  
  
> [!NOTE]
>  Elementy zawarte w `Task` elementu są specyficzne dla fabryki zadań, w tym przypadku fabryki zadań kodu.  
  
### <a name="code-element"></a>Element Code  
 Ostatni element podrzędny, które mają być wyświetlane w `Task` element jest `Code` elementu. `Code` Element zawiera lub lokalizuje kod, który ma być skompilowane w ramach zadania. Umieść w `Code` element zależy od tego, jak chcesz napisać zadanie.  
  
 `Language` Atrybut określa język, w którym napisano kod. Dopuszczalne wartości to `cs` dla języka C# `vb` dla języka Visual Basic.  
  
 `Type` Atrybut określa typ kodu, który można znaleźć w `Code` elementu.  
  
-   Jeśli wartość `Type` jest `Class`, a następnie `Code` element zawiera kod dla klasy, która pochodzi od klasy <xref:Microsoft.Build.Framework.ITask> interfejsu.  
  
-   Jeśli wartość `Type` jest `Method`, ten kod definiuje nadpisanie `Execute` metody <xref:Microsoft.Build.Framework.ITask> interfejsu.  
  
-   Jeśli wartość `Type` jest `Fragment`, ten kod definiuje zawartość `Execute` metody, ale nie podpisu lub `return` instrukcji.  
  
 Sam kod zwykle pojawia się między `<![CDATA[` znaczników i `]]>` znacznika. Ponieważ kod znajduje się w sekcji CDATA, nie masz już martwić się o zmianę znaczenia znaków zastrzeżonych, na przykład "\<" lub ">".  
  
 Alternatywnie, można użyć `Source` atrybutu `Code` element, aby określić lokalizację pliku, który zawiera kod dla zadania. Kod w pliku źródłowym musi być typu, który jest określony przez `Type` atrybutu. Jeśli `Source` atrybut był obecny, wartość domyślna `Type` jest `Class`. Jeśli `Source` jest nieobecna, wartość domyślna to `Fragment`.  
  
> [!NOTE]
>  Podczas definiowania klasy zadań w pliku źródłowym, nazwa klasy należy uzgodnić z `TaskName` atrybut odpowiadającego [UsingTask](../msbuild/usingtask-element-msbuild.md) elementu.  
  
## <a name="hello-world"></a>Witaj Świecie  
 Poniżej przedstawiono bardziej niezawodne zadania wbudowanego. Wyświetla zadania HelloWorld "Hello, world!" na domyślne urządzenie rejestrowania błędów, który jest zazwyczaj konsoli systemowej lub Visual Studio **dane wyjściowe** okna. `Reference` Elementu w przykładzie jest dołączony tylko do celów ilustracyjnych.  
  
```  
<Project ToolsVersion="12.0" xmlns="http://schemas.microsoft.com/developer/msbuild/2003">  
  <!-- This simple inline task displays "Hello, world!" -->  
  <UsingTask  
    TaskName="HelloWorld"  
    TaskFactory="CodeTaskFactory"  
    AssemblyFile="$(MSBuildToolsPath)\Microsoft.Build.Tasks.v4.0.dll" >  
    <ParameterGroup />  
    <Task>  
      <Reference Include="System.Xml"/>  
      <Using Namespace="System"/>  
      <Using Namespace="System.IO"/>  
      <Code Type="Fragment" Language="cs">  
<![CDATA[  
// Display "Hello, world!"  
Log.LogError("Hello, world!");  
]]>  
      </Code>  
    </Task>  
  </UsingTask>  
</Project>  
```  
  
 Można zapisać zadania HelloWorld w pliku o nazwie HelloWorld.targets, a następnie wywołać go z projektu w następujący sposób.  
  
```  
<Project ToolsVersion="4.0" xmlns="http://schemas.microsoft.com/developer/msbuild/2003">  
  <Import Project="HelloWorld.targets" />  
  <Target Name="Hello">  
    <HelloWorld />  
  </Target>  
</Project>  
```  
  
## <a name="input-and-output-parameters"></a>Dane wejściowe i parametry wyjściowe  
 Parametry zadania wbudowane są elementami podrzędnymi `ParameterGroup` elementu. Każdy parametr przyjmuje nazwę elementu, który go definiuje. Poniższy kod definiuje parametru `Text`.  
  
```  
<ParameterGroup>  
    <Text />  
</ParameterGroup>  
```  
  
 Parametry może mieć co najmniej jeden z tych atrybutów:  
  
-   `Required` jest opcjonalny atrybut, który jest `false` domyślnie. Jeśli `true`, a następnie parametr jest wymagany i musi być danej wartości przed wywołaniem zadania.  
  
-   `ParameterType` jest opcjonalny atrybut, który jest `System.String` domyślnie. Mogą posłużyć do w pełni kwalifikowaną typu, elementu lub wartości, który może zostać przekonwertowany do i z ciągu za pomocą System.Convert.ChangeType. (Innymi słowy, dowolnej typ, który mogą być przekazywane do i z zadania zewnętrznego.)  
  
-   `Output` jest opcjonalny atrybut, który jest `false` domyślnie. Jeśli `true`, a następnie parametru musi być danej wartości przed powrotem z metody Execute.  
  
 Na przykład  
  
```  
<ParameterGroup>  
    <Expression Required="true" />  
      <Files ParameterType="Microsoft.Build.Framework.ITaskItem[]" Required="true" />  
    <Tally ParameterType="System.Int32" Output="true" />  
</ParameterGroup>  
```  
  
 definiuje trzy następujące parametry:  
  
-   `Expression` jest wymagany parametr wejściowy typu System.String.  
  
-   `Files` jest wymagany element parametr wejściowy listy.  
  
-   `Tally` jest parametrem wyjściowym typu System.Int32.  
  
 Jeśli `Code` element ma `Type` atrybutu `Fragment` lub `Method`, a następnie właściwości są tworzone automatycznie dla każdego parametru. W przeciwnym razie właściwości musi być jawnie zadeklarowana w kodzie źródłowym zadań i muszą dokładnie odpowiadać ich definicji parametru.  
  
## <a name="example"></a>Przykład  
 Następujące zadania wbudowanego zamienia każde wystąpienie tokenu w danym pliku z danej wartości.  
  
```  
<Project xmlns='http://schemas.microsoft.com/developer/msbuild/2003' ToolsVersion="12.0">  
  
  <UsingTask TaskName="TokenReplace" TaskFactory="CodeTaskFactory" AssemblyFile="$(MSBuildToolsPath)\Microsoft.Build.Tasks.v12.0.dll">  
    <ParameterGroup>  
      <Path ParameterType="System.String" Required="true" />  
      <Token ParameterType="System.String" Required="true" />  
      <Replacement ParameterType="System.String" Required="true" />  
    </ParameterGroup>  
    <Task>  
      <Code Type="Fragment" Language="cs"><![CDATA[  
string content = File.ReadAllText(Path);  
content = content.Replace(Token, Replacement);  
File.WriteAllText(Path, content);  
  
]]></Code>  
    </Task>  
  </UsingTask>  
  
  <Target Name='Demo' >  
    <TokenReplace Path="C:\Project\Target.config" Token="$MyToken$" Replacement="MyValue"/>  
  </Target>  
</Project>  
```  
  
## <a name="see-also"></a>Zobacz też  
 [Zadania](../msbuild/msbuild-tasks.md)   
 [Przewodnik: Tworzenie zadania wbudowanego](../msbuild/walkthrough-creating-an-inline-task.md)



