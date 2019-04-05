---
title: Nutzen Bibliotheken und Komponenten in C++-Projekten
ms.date: 12/10/2018
f1_keywords:
- VC.Project.References
helpviewer_keywords:
- Add References Dialog Box (C++)
- .NET Framework (C++), Add References Dialog Box
ms.assetid: 12b8f571-0f21-40b3-9404-5318a57e9cb5
ms.openlocfilehash: dff057977e6b6ff0c36d3a888bc4d5c3aa778576
ms.sourcegitcommit: c7f90df497e6261764893f9cc04b5d1f1bf0b64b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/05/2019
ms.locfileid: "59038762"
---
# <a name="consuming-libraries-and-components"></a>Nutzen Bibliotheken und Komponenten

Häufig ein C++-Projekt benötigt, Funktionen aufzurufen oder Zugriff auf Daten in eine binäre Datei, z. B. statische Bibliothek (LIB-Dateien), DLL, Windows-Runtime-Komponente, die COM-Komponente oder .NET Framework-Assembly. In diesen Fällen müssen Sie das Projekt so konfigurieren, dass zum Zeitpunkt der Erstellung der Binärdatei gefunden werden kann. Die jeweiligen Schritte hängen von den Typ des Projekts, den Typ der Binärdatei, und gibt an, ob die Binärdatei in der gleichen Projektmappe wie Ihr Projekt erstellt wird. 

## <a name="consuming-libraries-downloaded-via-vcpkg"></a>Verwenden von Bibliotheken heruntergeladen über vcpkg

Um eine Bibliothek nutzen, die Sie mithilfe von heruntergeladen haben die **Vcpkg** -Paket-Manager können Sie die nachstehenden Anweisungen ignorieren. Weitere Informationen finden Sie unter [vcpkg: Ein C++-Paket-Manager für Windows, Linux und MacOS](vcpkg.md#integrate-with-visual-studio-windows) für Weitere Informationen.

## <a name="consuming-static-libraries"></a>Verwenden von statischen Bibliotheken

Wenn Ihr Projekt für die statische Bibliothek in der gleichen Projektmappe erstellt wird:

1. #<a name="include-the-header-files-for-the-static-library-using-quotation-marks-in-a-typical-solution-the-path-will-start-with-library-project-name-intellisense-will-help-you-find-it"></a>enthalten Sie die Header-Dateien für die statische Bibliothek mithilfe der Anführungszeichen ein. Der Pfad beginnt in einer typischen Lösung mit `../<library project name>`. IntelliSense hilft Ihnen bei der Suche.
2. Fügen Sie einen Verweis auf das statische Bibliotheksprojekt hinzu. Mit der rechten Maustaste auf **Verweise** unter dem Projektknoten "Anwendung" im **Projektmappen-Explorer** , und wählen Sie **Verweis hinzufügen**. 

Wenn die statische Bibliothek, die nicht Teil der Lösung ist:

1. Mit der rechten Maustaste auf den Projektknoten der Anwendung im **Projektmappen-Explorer** und wählen Sie dann **Eigenschaften**. 
2. In der **VC++-Verzeichnisse** Eigenschaft Seite, fügen Sie den Pfad zu dem Verzeichnis, in denen befindet sich die LIB-Datei im **Bibliothekspfade** und fügen Sie den Pfad, um die Bibliothek-Header-Dateien in **Includeverzeichnisse** .  
3. In der **Linker > Eingabe** Eigenschaft Seite, fügen Sie den Namen der LIB-Datei zu **zusätzliche Abhängigkeiten**.

## <a name="dynamic-link-libraries"></a>Dynamic Link Librarys

Wenn die DLL als Teil der gleichen Projektmappe wie die Anwendung erstellt wird, führen Sie die gleichen Schritte wie für eine statische Bibliothek.

Wenn die DLL, die nicht Teil der Anwendungslösung ist, benötigen Sie die DLL-Datei, die einem oder mehreren Headern mit Prototypen für die exportierten Funktionen und Klassen und eine LIB-Datei, die die erforderlichen Informationen für die Verknüpfung bereitstellt.

1. Kopieren Sie die DLL in den Ausgabeordner des Projekts oder in einen anderen Ordner in den standardmäßigen Windows-Suchpfad für DLL-Dateien. Finden Sie unter [Dynamic Link Library Search Order](/windows/desktop/dlls/dynamic-link-library-search-order).
2. Führen Sie die Schritte 1 bis 3 für statische Bibliotheken, um die Pfade zu den Headern und LIB-Datei bereitzustellen.

## <a name="com-objects"></a>COM-Objekte

Wenn die native C++-Anwendung benötigt, um ein COM-Objekt zu nutzen, und dieses Objekt *registriert*, dann ist alles, was Sie tun CoCreateInstance und übergeben die CLSID des Objekts. Das System befindet sich in der Windows-Registrierung und zu laden. C++ / CLI-Projekt kann ein COM-Objekt nutzen, auf die gleiche Weise oder durch Hinzufügen eines Verweises aus der **Verweise hinzufügen > COM** Liste und Ihre Verwendung durch die [RCW](/dotnet/framework/interop/runtime-callable-wrapper). 

## <a name="net-assemblies-and-windows-runtime-components"></a>.NET-Assemblys und Windows-Runtime-Komponenten

In UWP- oder C++ / CLI-Projekten, nutzen Sie .NET-Assemblys oder Windows-Runtime-Komponenten durch Hinzufügen einer *Verweis* auf die Assembly oder Komponente. Unter den **Verweise** Knoten in einem UWP oder C++ / CLI-Projekt sehen Sie Verweise auf die häufig verwendeten Komponenten. Mit der rechten Maustaste auf die **Verweise** Knoten **Projektmappen-Explorer** um die **Verweis-Manager** , und navigieren Sie über zusätzliche Komponenten, die mit dem System bekannt sind. Klicken Sie auf die **Durchsuchen** Schaltfläche, um zu einem beliebigen Ordner zu navigieren, in denen eine benutzerdefinierte Komponente befindet. Da Assemblys von .NET und Windows-Runtime-Komponenten integrierte Typinformationen enthalten, sehen Sie ihre Methoden und Klassen, indem Sie mit der rechten Maustaste, und wählen **im Objektkatalog anzeigen**. 

## <a name="reference-properties"></a>Verweiseigenschaften

Jede Art von Verweis verfügt über Eigenschaften. Sie können die Eigenschaften anzeigen, indem Sie den Verweis im Projektmappen-Explorer auswählen und **ALT+EINGABE**drücken bzw. mit der rechten Maustaste klicken und **Eigenschaften**auswählen. Einige Eigenschaften sind schreibgeschützt, während andere geändert werden können. Allerdings müssen Sie diese Eigenschaften in der Regel nicht manuell ändern.

### <a name="activex-reference-properties"></a>ActiveX-Verweiseigenschaften

ActiveX-Verweiseigenschaften sind nur für Verweise auf COM-Komponenten verfügbar. Diese Eigenschaften werden nur angezeigt, wenn eine COM-Komponente im Bereich **Verweise** ausgewählt ist. Die Eigenschaften können nicht geändert werden.

- **Vollständiger Pfad des Steuerelements**

   Zeigt den Verzeichnispfad des Steuerelements an, auf das verwiesen wird.

- **GUID des Steuerelements**

   Zeigt de GUID für das ActiveX-Steuerelement an.

- **Steuerelementversion**

   Zeigt die Version des ActiveX-Steuerelements an, auf das verwiesen wird.

- **Typbibliotheksnamen**

   Zeigt den Namen der Typbibliothek an, auf die verwiesen wird.

- **Wrappertool**

   Zeigt das Tool an, das zum Erstellen der Interop-Assembly aus der COM-Bibliothek oder dem ActiveX-Steuerelement verwendet wird, auf die bzw. das verwiesen wird.

### <a name="assembly-reference-properties-ccli"></a>Assemblyverweiseigenschaften (C++ / CLI)

Assemblyverweiseigenschaften stehen nur für Verweise auf .NET Framework-Assemblys in C++ / CLI-Projekten. Diese Eigenschaften werden nur angezeigt, wenn .NET Framework-Assembly ausgewählt ist die **Verweise** Bereich. Die Eigenschaften können nicht geändert werden.

- **Relativer Pfad**

   Zeigt den relativen Pfad vom Projektverzeichnis zur Assembly an, auf die verwiesen wird.

### <a name="build-properties"></a>Buildeigenschaften

Die folgenden Eigenschaften stehen für verschiedene Arten von Verweisen zur Verfügung. Sie ermöglichen Ihnen die Angabe, wie die Erstellung mit Verweisen erfolgen soll.

- **Lokale Kopie**

   Gibt an, ob die Assembly, auf die verwiesen wird, während eines Buildvorgangs automatisch an den Zielspeicherort kopiert wird.

- **Lokale Satellitenassemblys kopieren (C++ / CLI)**

   Gibt an, ob die Satellitenassemblys der Assembly, auf die verwiesen wird, während eines Buildvorgangs automatisch an den Zielspeicherort kopiert werden. Wird nur verwendet, wenn **Lokale Kopie** den Wert **true** aufweist.

- **Verweisassemblyausgabe**

   Gibt an, dass die Assembly im Buildvorgang verwendet wird. Wenn **true**, wird die Assembly während des Buildvorgangs in der Befehlszeile des Compilers verwendet.

### <a name="project-to-project-reference-properties"></a>Interprojektverweiseigenschaften

Die folgenden Eigenschaften definieren einen *Projekt-zu-Projekt-Verweis* aus dem Projekt, das ausgewählt wird die **Verweise** Bereich in ein anderes Projekt in der gleichen Projektmappe. Weitere Informationen finden Sie unter [Verwalten von Verweisen in einem Projekt](/visualstudio/ide/managing-references-in-a-project).

- **Bibliothekabhängigkeiten verknüpfen**

   Wenn diese Eigenschaft **True**ist, fügt das Projektsystem in das abhängige Projekt die LIB-Dateien ein, die vom unabhängigen Projekt erstellt werden. Normalerweise geben Sie **True**an.

- **Projektbezeichner**

   Identifiziert eindeutig das unabhängige Projekt. Der Eigenschaftswert ist eine interne System-GUID, die nicht geändert werden kann.

- **Bibliothekabhängigkeitseingaben verwenden**

   Wenn diese Eigenschaft **False**ist, fügt das Projektsystem nicht in das abhängige Projekt die OBJ-Dateien für die Bibliothek ein, die vom unabhängigen Projekt erstellt wurden. Folglich deaktiviert dieser Wert inkrementelles Verknüpfen. In der Regel geben Sie **False** an, da das Erstellen der Anwendung lange dauern kann, wenn viele unabhängige Projekte vorhanden sind.

### <a name="read-only-reference-properties-com--net"></a>Eigenschaften für nur-Lese Verweis (COM und .NET)

Die folgenden Eigenschaften gelten für COM- und Assemblyverweise und können nicht geändert werden.

- **Assemblyname**

   Zeigt den Assemblynamen für die Assembly an, auf die verwiesen wird.

- **culture**

   Zeigt die Kultur des ausgewählten Verweises an.

- **Beschreibung**

   Zeigt die Beschreibung des ausgewählten Verweises an.

- **Vollständiger Pfad**

   Zeigt den Verzeichnispfad der Assembly an, auf die verwiesen wird.

- **Identität**

   Für die .NET Framework-Assemblys wird der vollständige Pfad angezeigt. Zeigt die GUID für COM-Komponenten an.

- **Bezeichnung**

   Zeigt die Bezeichnung des Verweises an.

- **Name**

   Zeigt den Namen des Verweises an.

- **Öffentliches Schlüsseltoken**

   Zeigt das öffentliche Schlüsseltoken zur Identifizierung der Assembly an, auf die verwiesen wird.

- **Starker Name**

   `true` , wenn die Assembly, auf die verwiesen wird, einen starken Namen hat. Eine Assembly mit starkem Namen verfügt über eine eindeutige Versionsangabe.

- **Version**

   Zeigt die Version der Assembly an, auf die verwiesen wird.

## <a name="see-also"></a>Siehe auch

[Referenz für C++-Projekt Seite](reference/property-pages-visual-cpp.md)<br>
[Festlegen von C++-Compiler und erstellen Sie die Eigenschaften in Visual Studio](working-with-project-properties.md)