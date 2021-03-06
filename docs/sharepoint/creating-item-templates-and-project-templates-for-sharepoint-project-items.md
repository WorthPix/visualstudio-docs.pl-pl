---
title: Utworzenie elementu szablonów i szablonów projektu dla elementów projektu SharePoint | Dokumentacja firmy Microsoft
ms.custom: ''
ms.date: 02/02/2017
ms.technology:
- office-development
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- SharePoint project items, creating custom templates
- .spdata files
- projects [SharePoint development in Visual Studio], creating custom templates
- SharePoint projects, creating custom templates
- SharePoint development in Visual Studio, creating custom project and item templates
- project items [SharePoint development in Visual Studio], creating custom templates
author: TerryGLee
ms.author: tglee
manager: douge
ms.workload:
- office
ms.openlocfilehash: 0d2d7d14b1e87a584da9f789c5092373db5519d5
ms.sourcegitcommit: e6b13898cfbd89449f786c2e8f3e3e7377afcf25
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 06/22/2018
ms.locfileid: "36327144"
---
# <a name="create-item-templates-and-project-templates-for-sharepoint-project-items"></a>Tworzenie szablonów elementów i szablonów projektu dla SharePoint — elementy projektu
  Podczas definiowania niestandardowego typu elementu projektu SharePoint, należy ją skojarzyć z elementu lub szablon projektu. To skojarzenie umożliwia innych deweloperom używanie elementu projektu w programie Visual Studio. Można również utworzyć Kreatora szablonu.

 Na przykład Visual Studio nie ma szablonu projektu lub elementu szablon umożliwiający dodanie pola do witryny programu SharePoint. Można zdefiniować typu elementu projektu SharePoint, która reprezentuje pole i następnie tworzenia szablonu elementu, który inni deweloperzy służy do dodawania elementu pola do projektu SharePoint. Alternatywnie można utworzyć szablon projektu, dzięki czemu deweloperzy mogą tworzyć nowy projekt programu SharePoint, który ma element pola. W obu przypadkach można też podać kreatora, który jest wyświetlany, gdy deweloperzy używać szablonu. Ten kreator może zbierać informacje z deweloperom konfigurowanie nowego elementu lub projekt.

 Szablony elementów i szablonów projektu są *.zip* pliki, które zawierają pliki, które są używane przez program Visual Studio do tworzenia projektu lub elementu projektu. Aby uzyskać więcej informacji na temat podstawy szablonów elementów i szablonów projektu, zobacz [Tworzenie szablonów projektów i elementów](../ide/creating-project-and-item-templates.md).

## <a name="create-item-templates"></a>Tworzenie szablonów elementów
 Podczas tworzenia szablonu elementów dla elementu projektu SharePoint są niektóre pliki, które są zawsze wymagane i opcjonalne pliki, które mogą być używane przez niektórych typów elementów projektu. Aby uzyskać wskazówki, który demonstruje sposób definiowania typu elementu projektu SharePoint i utworzyć szablon elementu dla niego, zobacz [wskazówki: Tworzenie elementu projektu akcji niestandardowej z szablonem elementu, część 1](../sharepoint/walkthrough-creating-a-custom-action-project-item-with-an-item-template-part-1.md).

 W poniższej tabeli wymieniono pliki wymagane do utworzenia szablonu elementów dla elementu projektu SharePoint.

|Wymaganego pliku|Opis|
|-------------------|-----------------|
|*.Spdata —* pliku|Ten plik XML określa zawartości i domyślne zachowanie elementu projektu. Ten plik musi być uwzględniona w szablonie elementu. Aby uzyskać więcej informacji o zawartości *.spdata —* plików, zobacz [odwołanie do schematu elementu projektu SharePoint](../sharepoint/sharepoint-project-item-schema-reference.md).|
|A *.vstemplate* pliku.|Ten plik dostarcza informacje wymagane do wyświetlenia szablonu w Visual Studio **Dodaj nowy element** okno dialogowe i utworzyć element projektu z szablonu. Ten plik musi być uwzględniona w szablonie elementu. Aby uzyskać więcej informacji, zobacz [pliki metadanych szablonów programu Visual Studio](http://msdn.microsoft.com/en-us/129d59b5-7f9c-4daf-9832-eaedb3c4c961).|
|Zestawu rozszerzenia programu Visual Studio, który implementuje <xref:Microsoft.VisualStudio.SharePoint.ISharePointProjectItemTypeProvider> interfejsu.|Ten zestaw definiuje zachowanie czas wykonywania elementu projektu. Ten zestaw musi być uwzględniona w pakiet VSIX przy użyciu szablonu elementu. Aby uzyskać więcej informacji, zobacz [Definiowanie niestandardowych typów elementów projektu SharePoint](../sharepoint/defining-custom-sharepoint-project-item-types.md) i [wdrażanie rozszerzeń dla narzędzi SharePoint w Visual Studio](../sharepoint/deploying-extensions-for-the-sharepoint-tools-in-visual-studio.md).|

 W poniższej tabeli wymieniono niektóre z najczęściej używane pliki opcjonalne, które można uwzględnić w szablonie elementu. Niektórych typów elementów projektu może wymagać innych plików, które nie są wyświetlane tutaj.

|Opcjonalny plik|Opis|
|-------------------|-----------------|
|*Elements.XML*|A *element funkcji* pliku. Ten plik definiuje interfejsu użytkownika i zachowanie dostosowania utworzone przez element projektu. Każdy typ dostosowania, takie jak wystąpienia listy, typy zawartości lub akcje niestandardowe ma inny schemat, który definiuje zawartość tego pliku. Aby uzyskać więcej informacji, zobacz [bloków konstrukcyjnych: funkcje](http://go.microsoft.com/fwlink/?LinkId=169183) i [schematy funkcji](http://go.microsoft.com/fwlink/?LinkId=169192).|
|*Schema.XML*|Plik schematu dla definicje list. Aby uzyskać więcej informacji, zobacz [bloków konstrukcyjnych: list i bibliotek dokumentów](http://go.microsoft.com/fwlink/?LinkId=177792) i [Schema.xml](http://go.microsoft.com/fwlink/?LinkId=177793).|
|*.WebPart*|A *definicji składnika Web Part* pliku. Ten plik zawiera ustawienia właściwości części sieci Web. Aby uzyskać więcej informacji, zobacz [bloków konstrukcyjnych: części sieci Web](http://go.microsoft.com/fwlink/?LinkId=177791).|
|*.ascx*|Plik UserControl programu ASP.NET. Ten plik Określa interfejs użytkownika programu Visual Web Part.|
|*.aspx*|Plik strony ASP.NET. Ten plik zawiera znaczników XML, który definiuje strony aplikacji.|
|*.cs* lub *.vb* plików|Te pliki kodu zdefiniuj zachowanie dostosowania programu SharePoint, które ma modelu programowania, które są dostępne z Visual C# lub Visual Basic kodu, na przykład stron aplikacji, składników Web Part i przepływów pracy.|
## <a name="create-project-templates"></a>Tworzenie szablonów projektu
 Podczas tworzenia szablonu projektu programu SharePoint, istnieją pewne pliki, które są zawsze plików wymaganych i opcjonalnych, które mogą być używane przez niektóre rodzaje projektów. SharePoint — projekty obejmują zazwyczaj co najmniej jeden element projektu programu SharePoint. Jednak nie jest to wymagane. Na przykład można zdefiniować szablon projektu programu SharePoint, która powinna być stosowana wyłącznie do wdrażania rozwiązań programu SharePoint utworzonych w innych projektach.

 Aby uzyskać wskazówki, który demonstruje sposób definiowania typu elementu projektu SharePoint i utworzyć dla niego szablon projektu, zobacz [wskazówki: Tworzenie elementu projektu kolumn witryny z szablonem projektu, część 1](../sharepoint/walkthrough-creating-a-site-column-project-item-with-a-project-template-part-1.md).

 W poniższej tabeli wymieniono pliki, które muszą być zawarte w szablonie projektu programu SharePoint.

|Wymaganego pliku|Opis|
|-------------------|-----------------|
|A *.vstemplate* pliku|Ten plik dostarcza informacje wymagane do wyświetlenia szablonu w Visual Studio **nowy projekt** okno dialogowe i utworzyć projekt z szablonu. Aby uzyskać więcej informacji, zobacz [pliki metadanych szablonów programu Visual Studio](http://msdn.microsoft.com/en-us/129d59b5-7f9c-4daf-9832-eaedb3c4c961).|
|A *.csproj* lub *vbproj* pliku|To jest plik projektu. Definiuje ustawienia konfiguracji projektu i zawartość.|
|*Package.Package*|Ten plik definiuje pakiet wdrażania dla projektu. Gdy Dostosowywanie pakietu rozwiązania dla projektu za pomocą projektanta pakietu Visual Studio przechowuje dane dotyczące pakietu rozwiązania w tym pliku.<br /><br /> Podczas tworzenia niestandardowego szablonu projektu programu SharePoint, zaleca się że obejmuje tylko minimalne wymagane zawartość w *Package.package* plików i konfigurowanie pakietu rozwiązania przy użyciu interfejsów API w <xref:Microsoft.VisualStudio.SharePoint.Packages> przestrzeń nazw w rozszerzeniu, który jest skojarzony z szablonem projektu. Jeśli to zrobisz, szablon projektu jest chronione przed przyszłych zmian w strukturze *Package.package* pliku. Na przykład, który demonstruje sposób tworzenia *Package.package* zawartość pliku z minimalnym wymaganiem, zobacz [wskazówki: Tworzenie elementu projektu kolumn witryny z szablonem projektu, część 1](../sharepoint/walkthrough-creating-a-site-column-project-item-with-a-project-template-part-1.md).<br /><br /> Jeśli chcesz zmodyfikować *Package.package* pliku bezpośrednio, zawartość można sprawdzić za pomocą schematu w *% Program Files (11.0\Xml\Schemas\PackageModelSchema.xsd programu Visual Studio x86)%\Microsoft* .|
|*Package.Template.xml*|Ten plik stanowi podstawę dla pliku manifestu rozwiązania (*manifest.xml*) dla pakietu rozwiązania programu SharePoint (*WSP*) wygenerowanych z projektu. Można dodać zawartości do tego pliku, jeśli chcesz określić niektóre zachowania, które nie mają być zmieniane przez użytkowników tego typu projektu. Aby uzyskać więcej informacji, zobacz [bloków konstrukcyjnych: rozwiązań](http://go.microsoft.com/fwlink/?LinkId=169186) i [schematu rozwiązania](http://go.microsoft.com/fwlink/?LinkId=177794).<br /><br /> Podczas tworzenia pakietu rozwiązań z projektu programu Visual Studio Scala zawartość *Package.package* i *Package.Template.xml* pliku manifestu plików do rozwiązania. Aby uzyskać więcej informacji o tworzeniu pakietów rozwiązania, zobacz [porady: Tworzenie pakietu rozwiązania SharePoint przy użyciu zadań MSBuild](../sharepoint/how-to-create-a-sharepoint-solution-package-by-using-msbuild-tasks.md).|

 W poniższej tabeli wymieniono pliki opcjonalne, które można uwzględnić w szablonie projektu.

|Opcjonalny plik|Opis|
|-------------------|-----------------|
|SharePoint — Elementy projektu|Może zawierać jeden lub więcej plików .spdata — które Definiowanie typów elementów projektu SharePoint. Każdy *.spdata —* plik musi mieć zgodną <xref:Microsoft.VisualStudio.SharePoint.ISharePointProjectItemTypeProvider> implementacją w zestawie rozszerzenia, do którego jest dołączony do pakietu VSIX z szablonem projektu. Aby uzyskać więcej informacji, zobacz [Tworzenie szablonów elementu](#creatingitemtemplates).<br /><br /> SharePoint — projekty obejmują zazwyczaj co najmniej jeden element projektu programu SharePoint. Jednak nie jest to wymagane.|
|*\<Nazwa_funkcji > .feature*|Ten plik definiuje funkcja programu SharePoint, która służy do grupowania kilka elementów projektu dla wdrożenia. Gdy dostosowywanie funkcji w projekcie za pomocą projektanta funkcji programu Visual Studio przechowuje dane dotyczące funkcji w tym pliku. Jeśli chcesz grupować elementy projektu do różnych funkcji, można dołączyć wielu *.feature* plików.<br /><br /> Podczas tworzenia niestandardowego szablonu projektu programu SharePoint, firma Microsoft zaleca obejmują minimalnej wymaganej zawartości w każdym *.feature* plików i konfigurowania funkcji za pomocą interfejsów API w <xref:Microsoft.VisualStudio.SharePoint.Features> przestrzeni nazw w rozszerzenie skojarzone z szablonem projektu. Jeśli to zrobisz, szablon projektu jest chronione przed przyszłych zmian w strukturze *.feature* pliku. Na przykład, który demonstruje sposób tworzenia *.feature* zawartość pliku z minimalnym wymaganiem, zobacz [wskazówki: Tworzenie elementu projektu kolumn witryny z szablonem projektu, część 1](../sharepoint/walkthrough-creating-a-site-column-project-item-with-a-project-template-part-1.md).<br /><br /> Jeśli chcesz zmodyfikować *.feature* pliku bezpośrednio, zawartość można sprawdzić za pomocą schematu w *% Program Files (11.0\Xml\Schemas\FeatureModelSchema.xsd programu Visual Studio x86)%\Microsoft*.|
|*\<Nazwa_funkcji >. Template.XML*|Ten plik stanowi podstawę dla pliku manifestu funkcji (*Feature.xml*) dla każdej funkcji, które są generowane na podstawie projektu. Można dodać zawartości do tego pliku, jeśli chcesz określić niektóre zachowania, które nie mają być zmieniane przez użytkowników tego typu projektu. Aby uzyskać więcej informacji, zobacz [bloków konstrukcyjnych: funkcje](http://go.microsoft.com/fwlink/?LinkId=169183) i [Feature.xml](http://go.microsoft.com/fwlink/?LinkId=177795) plików.<br /><br /> Podczas tworzenia pakietu rozwiązań z projektu programu Visual Studio Scala zawartość każdej pary  *\<Nazwa_funkcji > .feature* pliku i  *\<Nazwa_funkcji >. Template.XML* pliki do funkcji pliku manifestu. Aby uzyskać więcej informacji o tworzeniu pakietów rozwiązania, zobacz [porady: Tworzenie pakietu rozwiązania SharePoint przy użyciu zadań MSBuild](../sharepoint/how-to-create-a-sharepoint-solution-package-by-using-msbuild-tasks.md).|

## <a name="create-wizards-for-item-templates-and-project-templates"></a>Tworzenie kreatorów szablonów elementów i szablonów projektu
 Po zdefiniowaniu typu elementu projektu SharePoint i skojarzyć go z szablonem elementu lub projektu, można również utworzyć kreatora. Kreator wyświetli, gdy projektant używa szablonu elementów do dodania do projektu dla elementu projektu SharePoint lub gdy dewelopera używa szablonu projektu, aby utworzyć nowy projekt, który zawiera element projektu SharePoint. Kreator może służyć do zbierania informacji z deweloperzy i zainicjować element projektu programu SharePoint.

 Aby uzyskać wskazówki, które przedstawiają sposób Tworzenie kreatorów szablonów elementów i szablonów projektu, zobacz [wskazówki: Tworzenie elementu projektu akcji niestandardowej z szablonem elementu, część 2](../sharepoint/walkthrough-creating-a-custom-action-project-item-with-an-item-template-part-2.md) i [wskazówki: tworzenie witryny elementu projektu kolumn z szablonem projektu, część 2](../sharepoint/walkthrough-creating-a-site-column-project-item-with-a-project-template-part-2.md).

## <a name="see-also"></a>Zobacz także

- [Definiowanie niestandardowych typów elementów projektu SharePoint](../sharepoint/defining-custom-sharepoint-project-item-types.md)
- [Wskazówki: Tworzenie elementu projektu akcji niestandardowej z szablonem elementu, część 1](../sharepoint/walkthrough-creating-a-custom-action-project-item-with-an-item-template-part-1.md)
- [Wskazówki: Tworzenie elementu projektu akcji niestandardowej z szablonem elementu, część 2](../sharepoint/walkthrough-creating-a-custom-action-project-item-with-an-item-template-part-2.md)
- [Wskazówki: Tworzenie elementu projektu kolumn witryny z szablonem projektu, część 1](../sharepoint/walkthrough-creating-a-site-column-project-item-with-a-project-template-part-1.md)
- [Wskazówki: Tworzenie elementu projektu kolumn witryny z szablonem projektu, część 2](../sharepoint/walkthrough-creating-a-site-column-project-item-with-a-project-template-part-2.md)
- [Tworzenie szablonów projektów i elementów](../ide/creating-project-and-item-templates.md)
