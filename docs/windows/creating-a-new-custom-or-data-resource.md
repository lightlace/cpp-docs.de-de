---
title: "Creating a New Custom or Data Resource"
ms.custom: na
ms.date: "12/14/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "article"
f1_keywords: 
  - "vc.editors.binary"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "custom resources [C++]"
  - "data resources [C++]"
  - "resources [Visual Studio], creating"
ms.assetid: 9918bf96-38fa-43a1-a384-572f95d84950
caps.latest.revision: 13
caps.handback.revision: "9"
ms.author: "mblome"
manager: "ghogen"
---
# Creating a New Custom or Data Resource
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Sie können eine neue benutzerdefinierte oder Datenressource erstellen, indem Sie die Ressource mithilfe der normalen Syntax von Ressourcenskriptdateien \(RC\) in einer separaten Datei platzieren und dann die Datei einschließen, indem Sie im Projektmappen\-Explorer mit der rechten Maustaste auf das Projekt und dann im Kontextmenü auf **Ressourcenincludes** klicken.  
  
### So erstellen Sie eine neue benutzerdefinierte oder Datenressource  
  
1.  [Erstellen Sie eine RC\-Datei](../windows/how-to-create-a-resource-script-file.md), die die benutzerdefinierte oder Datenressource enthält.  
  
     Sie können benutzerdefinierte Daten in einer RC\-Datei als in Anführungszeichen eingeschlossene nullterminierte Zeichenfolgen oder als ganze Zahlen im dezimalen, hexadezimalen oder oktalen Format eingeben.  
  
2.  Klicken Sie im **Projektmappen\-Explorer** mit der rechten Maustaste auf die RC\-Datei Ihres Projekts, und klicken Sie dann im Kontextmenü auf **Ressourcenincludes**.  
  
3.  Geben Sie im Feld **Kompilierzeitdirektiven** eine **\#include**\-Anweisung ein, die den Namen der Datei angibt, die Ihre benutzerdefinierte Ressource enthält. Zum Beispiel:  
  
    ```  
    #include mydata.rc  
    ```  
  
     Achten Sie auf die korrekte Syntax und Rechtschreibung Ihrer Eingaben. Der Inhalt des Felds **Kompilierzeitdirektiven** wird in die Ressourcenskriptdatei genau so eingefügt, wie sie ihn eingegeben haben.  
  
4.  Klicken Sie auf **OK**, um Ihre Änderungen aufzuzeichnen.  
  
 Eine weitere Möglichkeit zum Erstellen einer benutzerdefinierten Ressource ist das Importieren einer externen Datei als benutzerdefinierte Ressource. Weitere Informationen finden Sie unter [Importieren und Exportieren von Ressourcen](../windows/how-to-import-and-export-resources.md).  
  
 Informationen zum Hinzufügen von Ressourcen zu verwalteten Projekten finden Sie unter [Ressourcen in Anwendungen](../Topic/Resources%20in%20Desktop%20Apps.md) im *.NET Framework\-Entwicklerhandbuch.* Informationen zum manuellen Hinzufügen von Ressourcendateien zu verwalteten Projekten, zum Zugreifen auf Ressourcen, zum Anzeigen statischer Ressourcen und zum Zuweisen von Ressourcenzeichenfolgen zu Eigenschaften finden Sie unter [Exemplarische Vorgehensweise: Lokalisieren von Windows Forms](assetId:///9a96220d-a19b-4de0-9f48-01e5d82679e5) und [Walkthrough: Using Resources for Localization with ASP.NET](../Topic/Walkthrough:%20Using%20Resources%20for%20Localization%20with%20ASP.NET.md).  
  
 Anforderungen  
  
 Win32  
  
## Siehe auch  
 [Binary Editor](../mfc/binary-editor.md)