---
title: Hinzufügen von Verweisen in Visual C++-Projekten | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-ide
ms.topic: conceptual
f1_keywords:
- VC.Project.References
dev_langs:
- C++
helpviewer_keywords:
- Add References Dialog Box (C++)
- .NET Framework (C++), Add References Dialog Box
ms.assetid: 12b8f571-0f21-40b3-9404-5318a57e9cb5
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: b372959105407074cd2a7295837e2c47ef629da7
ms.sourcegitcommit: 8480f16893f09911f08a58caf684405404f7ac8e
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/12/2018
ms.locfileid: "49162164"
---
# <a name="adding-references-in-visual-c-projects"></a>Hinzufügen von Verweisen in Visual C++-Projekten

Es kommt bei Programmen sehr häufig vor, dass in anderen Binärdateien (z. B. DLL-Dateien, Windows-Runtime-Komponenten, SDK-Erweiterungen, COM-Komponenten und .NET-Assemblys) APIs aufgerufen werden. Die Methode, mit der Ihr Programm diese anderen Binärdateien findet, hängt sowohl vom Projekttyp als auch vom Typ der Binärdatei ab.

In einem systemeigenen C++-Projekt verwenden Sie „LoadLibrary“ oder „CoCreateInstance“, um den Pfad zur Binärdatei anzugeben, wenn Sie eine systemeigene DLL-Datei oder COM-Komponente verwenden, die nicht von einem anderen Projekt in Ihrer Projektmappe erzeugt wird. Andernfalls lassen Sie die Binärdatei vom System aufspüren, indem es an bestimmten klar definierten Speicherorten sucht.

In anderen Projekttypen, z. B. UWP-Projekten oder C++/CLI-Projekten, oder bei Binärdateien, die von einem anderen Projekt in der Projektmappe erstellt wurden, fügen Sie der Assembly, der Komponente oder dem Projekt einen *Verweis* hinzu.   Ein Verweis besteht im Wesentlichen aus einem Satz von Daten, der es dem Programm ermöglicht, die Binärdatei zu finden und mit ihr zu kommunizieren.       Wenn Sie einen Verweis hinzufügen, kümmert sich Visual Studio um die Low-Level-Details. Klicken Sie mit der rechten Maustaste im **Projektmappen-Explorer** auf den Knoten **Verweise**, um den **Verweis-Manager** zu öffnen, mit dem Sie Verweise von einem C++-Projekt auf .NET Framework-Assemblys (nur C++/CLI), COM-Komponenten und andere Projekte in Ihrer Projektmappe, einschließlich freigegebener Projekte oder verbundenen Diensten, festlegen können. Die Anzeige im Verweis-Manager variiert in Abhängigkeit vom Projekttyp.

In einem systemeigenen C++-Projekt (ATL) gilt das Konzept der *Verweise* nur für andere Projekte in der Projektmappe, einschließlich freigegebener Projekte, daher ist dies alles, was im **Verweis-Manager**angezeigt wird:

![Visual C&#43;&#43;-Verweis-Manager &#40;ATL-Projekte&#41;](../ide/media/visual-c---reference-manager--atl-projects-.png "Visual C++-Verweis-Manager (ATL-Projekte)")

In einem C++/CLI- oder UWP-Projekt (universelle Windows-Plattform) gilt das Konzept der Verweise zusätzlich zu anderen Projekten in der Projektmappe für verschiedene Arten von Binärdateien.  Diese werden alle im **Verweis-Manager**zu öffnen.

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

### <a name="assembly-reference-properties"></a>Assemblyverweiseigenschaften

Assemblyverweiseigenschaften sind nur für Verweise auf .NET Framework-Assemblys in C++/CLI-Projekten verfügbar. Diese Eigenschaften werden nur angezeigt, wenn eine .NET Framework-Assembly im Bereich **Verweise** ausgewählt ist. Die Eigenschaften können nicht geändert werden.

- **Relativer Pfad**

   Zeigt den relativen Pfad vom Projektverzeichnis zur Assembly an, auf die verwiesen wird.

### <a name="build-properties"></a>Buildeigenschaften

Die folgenden Eigenschaften stehen für verschiedene Arten von Verweisen zur Verfügung. Sie ermöglichen Ihnen die Angabe, wie die Erstellung mit Verweisen erfolgen soll.

- **Lokale Kopie**

   Gibt an, ob die Assembly, auf die verwiesen wird, während eines Buildvorgangs automatisch an den Zielspeicherort kopiert wird.

- **Lokale Satellitenassemblys kopieren**

   Gibt an, ob die Satellitenassemblys der Assembly, auf die verwiesen wird, während eines Buildvorgangs automatisch an den Zielspeicherort kopiert werden. Wird nur verwendet, wenn **Lokale Kopie** den Wert **true** aufweist.

- **Verweisassemblyausgabe**

   Gibt an, dass die Assembly im Buildvorgang verwendet wird. Wenn **true**, wird die Assembly während des Buildvorgangs in der Befehlszeile des Compilers verwendet.

### <a name="project-to-project-reference-properties"></a>Interprojektverweiseigenschaften

Die folgenden Eigenschaften definieren einen *Verweis zwischen Projekten* von dem im Bereich **Verweise** ausgewählten Projekt auf ein anderes Projekt in derselben Projektmappe. Weitere Informationen finden Sie unter [Verwalten von Verweisen in einem Projekt](/visualstudio/ide/managing-references-in-a-project).

- **Bibliothekabhängigkeiten verknüpfen**

   Wenn diese Eigenschaft **True**ist, fügt das Projektsystem in das abhängige Projekt die LIB-Dateien ein, die vom unabhängigen Projekt erstellt werden. Normalerweise geben Sie **True**an.

- **Projektbezeichner**

   Identifiziert eindeutig das unabhängige Projekt. Der Eigenschaftswert ist eine interne System-GUID, die nicht geändert werden kann.

- **Bibliothekabhängigkeitseingaben verwenden**

   Wenn diese Eigenschaft **False**ist, fügt das Projektsystem nicht in das abhängige Projekt die OBJ-Dateien für die Bibliothek ein, die vom unabhängigen Projekt erstellt wurden. Folglich deaktiviert dieser Wert inkrementelles Verknüpfen. In der Regel geben Sie **False** an, da das Erstellen der Anwendung lange dauern kann, wenn viele unabhängige Projekte vorhanden sind.

### <a name="reference-properties"></a>Verweiseigenschaften

Die folgenden Eigenschaften gelten für COM- und Assemblyverweise und können nicht geändert werden.

- **Assemblyname**

   Zeigt den Assemblynamen für die Assembly an, auf die verwiesen wird.

- **Kultur**

   Zeigt die Kultur des ausgewählten Verweises an.

- **Beschreibung**

   Zeigt die Beschreibung des ausgewählten Verweises an.

- **Vollständiger Pfad**

   Zeigt den Verzeichnispfad der Assembly an, auf die verwiesen wird.

- **Identity**

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

[Eigenschaftenseiten](../ide/property-pages-visual-cpp.md)<br>
[Arbeiten mit Projekteigenschaften](../ide/working-with-project-properties.md)