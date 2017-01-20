---
title: "HTML-Dateien"
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
  - "Benutzerdefinierte Assistenten, HTML-Dateien"
  - "Benutzerdefinierte Assistenten, Benutzeroberfläche"
  - "Dateien [C++], Erstellt durch einen benutzerdefinierten Assistenten"
  - "HTML-Seiten, Benutzeroberfläche für benutzerdefinierte Assistenten"
  - "Benutzeroberfläche für Assistenten"
  - "Assistenten [C++], Benutzeroberfläche für benutzerdefinierte Assistenten"
ms.assetid: 3b6ed080-6560-418b-b908-d84d71bdf145
caps.latest.revision: 6
caps.handback.revision: "6"
ms.author: "mblome"
manager: "ghogen"
---
# HTML-Dateien
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Ein Assistent kann über eine Benutzeroberfläche in Form einer HTML\-Oberfläche verfügen.  Neben Default.htm kann ein Assistent eine beliebige Anzahl von HTM\-Dateien umfassen, die Sie im [benutzerdefinierten Assistenten](../ide/custom-wizard.md) im Feld **Anzahl der Seiten** angeben.  Jede HTM\-Datei stellt eine HTML\-Seite des Assistenten dar. Der Zugriff auf die HTML\-Seiten erfolgt über die Schaltflächen **Weiter** und **Zurück**, über Registerkarten oder über ein beliebiges anderes Format, das Sie im Entwurf des Assistenten festlegen.  
  
 Die HTML\-Datei umfasst:  
  
-   Das **SYMBOL**\-Tag, das den Standardwert für benutzerdefinierte Optionen angibt.  Symbole werden in die Symboltabelle geschrieben, wenn der Benutzer auf **Fertig stellen** klickt. Beispiel:  
  
```  
<SYMBOL NAME='HEADER_FILE' VALUE='MyHeader.h' TYPE=text></SYMBOL>  
```  
  
 In einem in der Benutzeroberfläche des Assistenten enthaltenen Textfeld, das in der Symboltabelle als **HEADER\_FILE** gekennzeichnet ist, ist der Standardtext "MyHeader.h" aufgeführt.  Sie können diesen Wert in der Assistenten\-Benutzeroberfläche ändern. Der neue Wert wird in die Symboltabelle des Projekts geschrieben, wenn Sie auf **Fertig stellen** klicken. Beispiel:  
  
```  
<SYMBOL NAME='CHECKBOX1' TYPE=checkbox VALUE=false></SYMBOL>  
```  
  
 Das Kontrollkästchen, das in der Symboltabelle als "CHECKBOX1" gekennzeichnet ist, ist in der Assistenten\-Benutzeroberfläche standardmäßig deaktiviert.  Sie können dieses Kontrollkästchen in der HTML\-Benutzeroberfläche aktivieren. Der neue Wert wird in die Symboltabelle des Projekts geschrieben, wenn Sie auf **Fertig stellen** klicken.  
  
 Durch jede HTM\-Datei werden vom Benutzer ausgewählte Optionen in der Symboltabelle aufgezeichnet.  
  
-   Der Inhalt von [Common.js](../ide/customizing-cpp-wizards-with-common-jscript-functions.md) mit häufig verwendeten und nützlichen JScript\-Funktionen und **Default.js**.  
  
-   Verweise auf die Projektbilder, die auf der HTML\-Seite angezeigt werden.  
  
-   HTML\-Text und \-Formatierung, mit denen die Gestaltung der Benutzeroberfläche des Assistenten angepasst wird  
  
-   JScript\-Funktionen für den Zugriff auf das Visual C\+\+\-Assistentenobjektmodell, mit deren Hilfe das Verhalten des Assistenten angepasst wird.  Diese Funktionen befinden sich im HTML\-Seitenabschnitt mit der Überschrift "\<SCRIPT LANGUAGE\='JSCRIPT'\>", wie im folgenden Beispiel dargestellt.  
  
    > [!NOTE]
    >  Um von der HTML\-Seite auf das Assistenten\- und Umgebungsobjektmodell zuzugreifen, stellen Sie dem Objektmodellelement "window.external" voran.  
  
    ```  
    function InitDocument(document)  
    {  
       setDirection();  
  
       if (window.external.FindSymbol('DOCUMENT_FIRST_LOAD'))  
       {  
          // This function sets the default symbols based   
          // on the values specified in the SYMBOL tags above  
          //  
          window.external.SetDefaults(document);  
       }  
  
       // Load the document and initialize the controls   
       // with the appropriate symbol values  
       //  
       window.external.Load(document);  
    }  
    ```  
  
 Beim folgenden Beispiel handelt es sich um einen Assistenten in Form einer Konsolenanwendung:  
  
```  
<SYMBOL NAME='WIZARD_DIALOG_TITLE' TYPE=text VALUE='Console Application Wizard'></SYMBOL>  
  
<SYMBOL NAME='EMPTY_PROJECT' TYPE=checkbox VALUE=false></SYMBOL>  
<SYMBOL NAME='SUPPORT_ATL' TYPE=checkbox VALUE=false></SYMBOL>  
<SYMBOL NAME='SUPPORT_MFC' TYPE=checkbox VALUE=false></SYMBOL>  
```  
  
## Siehe auch  
 [Für den Assistenten erstellte Dateien](../ide/files-created-for-your-wizard.md)   
 [Benutzerdefinierter Assistent](../ide/custom-wizard.md)   
 [Erstellen eines benutzerdefinierten Assistenten](../ide/creating-a-custom-wizard.md)   
 [Entwerfen eines Assistenten](../ide/designing-a-wizard.md)