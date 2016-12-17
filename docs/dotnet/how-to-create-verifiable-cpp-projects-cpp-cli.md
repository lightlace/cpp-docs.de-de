---
title: "Gewusst wie: Erstellen &#252;berpr&#252;fbarer C++-Projekte (C++/CLI)"
ms.custom: na
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Konvertierungen, C++-Projekte"
  - "Überprüfbare Assemblys [C++], Erstellen"
  - "Visual C++-Projekte"
ms.assetid: 4ef2cc1a-e3e5-4d67-8d8d-9c614f8ec5d3
caps.latest.revision: 11
caps.handback.revision: "11"
ms.author: "mblome"
manager: "ghogen"
---
# Gewusst wie: Erstellen &#252;berpr&#252;fbarer C++-Projekte (C++/CLI)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Mit Visual C\+\+\-Anwendungs\-Assistenten können keine überprüfbaren Projekte erstellt werden, es können jedoch Projekte in überprüfbare Projekte konvertiert werden.  In diesem Thema wird beschrieben, wie Projekteigenschaften festgelegt und Quellcodedateien von Projekten geändert werden, um aus Visual C\+\+\-Projekte überprüfbare Anwendungen zu generieren.  
  
## Compiler\- und Linkereinstellungen  
 .NET\-Projekte verwenden standardmäßig das Compilerflag \/clr und konfigurieren den Linker für x86\-Hardware.  Für überprüfbaren Code müssen Sie das Flag \/clr:safe verwenden, und Sie müssen den Linker anweisen, statt systemeigene Maschinenbefehle MSIL zu generieren.  
  
#### So ändern Sie die Compiler\- und Linkereinstellungen  
  
1.  Zeigen Sie die Eigenschaftenseite des Projekts an.  Weitere Informationen finden Sie unter [Gewusst wie: Öffnen von Projekteigenschaftenseiten](../misc/how-to-open-project-property-pages.md).  
  
2.  Legen Sie auf der Seite **Allgemein** unter dem Knoten **Konfigurationseigenschaften** die **Common Language Runtime\-Unterstützung**\-Eigenschaft auf **Sichere MSIL Common Language Runtime\-Unterstützung \(\/clr:safe\)** fest.  
  
3.  Legen Sie auf der Seite **Erweitert** unter dem Knoten **Linker** die **CLR\-Bildtyp**\-Eigenschaft auf **Sicheres IL\-Bild erzwingen \(\/CLRIMAGETYPE: SAFE\)** fest.  
  
## Entfernen von systemeigenen Datentypen  
 Da systemeigene Datentypen auch dann nicht überprüfbar sind, wenn sie nicht verwendet werden, müssen alle Headerdateien mit systemeigenen Typen entfernt werden.  
  
> [!NOTE]
>  Die im Folgenden beschriebene Vorgehensweise bezieht sich auf Projekte für Windows Forms \(.NET\)\- und Konsolenanwendungsprojekte \(.NET\).  
  
#### So entfernen Sie Verweise auf systemeigene Datentypen  
  
1.  Kommentieren Sie in der Datei Stdafx.h alles aus.  
  
## Konfigurieren eines Einstiegspunktes  
 Da überprüfbare Anwendungen keine C\-Laufzeitbibliotheken \(CRT\) verwenden können, dürfen sie nicht von CRT abhängig sein, um die Hauptfunktion als Standardeinstiegspunkt aufzurufen.  Das bedeutet, dass Sie den Namen der Funktion explizit angeben müssen, die vom Linker beim Start aufgerufen werden soll. \(In diesem Fall wird zum Angeben eines CRT\-fremden Einstiegspunktes Main\(\) und nicht main\(\) oder \_tmain\(\) verwendet. Da der Einstiegspunkt explizit angegeben werden muss, ist dieser Name jedoch frei wählbar.\)  
  
> [!NOTE]
>  Die folgende Vorgehensweise bezieht sich auf Konsolenanwendungsprojekte \(.NET\).  
  
#### So konfigurieren Sie einen Einstiegspunkt  
  
1.  Ändern Sie in der Haupt\-CPP\-Datei des Projekts \_tmain \(\) in Main\(\).  
  
2.  Zeigen Sie die Eigenschaftenseite des Projekts an.  Weitere Informationen finden Sie unter [Gewusst wie: Öffnen von Projekteigenschaftenseiten](../misc/how-to-open-project-property-pages.md).  
  
3.  Geben Sie auf der Seite **Erweitert** unter dem Knoten **Linker** als **Einstiegspunkt**\-Eigenschaftswert `Main` ein.  
  
## Siehe auch  
 [Reiner und überprüfbarer Code](../dotnet/pure-and-verifiable-code-cpp-cli.md)