---
title: "CanUseFileName | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "CanUseFileName"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CanUseFileName-Methode"
ms.assetid: 60b669fa-9484-4435-b502-78ec8e960a00
caps.latest.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 6
---
# CanUseFileName
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Überprüft, ob eine Datei vorhanden ist.  Wenn die Datei existiert und nicht beschränkt ist, fordert der Assistent den Benutzer auf, den hinzuzufügenden Code mit der vorhandenen Datei zusammenzuführen.  
  
## Syntax  
  
```  
  
      function CanUseFileName(   
   strFileName,   
   bCheckIfMidlHeader,   
   bCannotExist,   
   bSetMergeFlag    
);  
```  
  
#### Parameter  
 `strFileName`  
 Der Name der zu überprüfenden Datei.  
  
 *bCheckIfMidlHeader*  
 Wird auf **true** gesetzt, um zu überprüfen, ob der Dateiname von MIDL generiert wird.  
  
 *bCannotExist*  
 Wird auf **true** gesetzt, um zu überprüfen, ob der Dateiname bereits vorhanden und nicht überschreibbar ist.  
  
 *bSetMergeFlag*  
 Wird auf **true** gesetzt, um das Symbol **MERG\_FILE** einzuschließen, das anzeigt, dass der Benutzer Code mit der bestehenden Datei zusammenführen kann.  
  
## Rückgabewert  
 **true**, wenn `strFileName` eindeutig ist, oder wenn der Code an die vorhandene Datei angehängt werden kann; andernfalls **false**.  
  
## Hinweise  
 Rufen Sie diese Funktion auf, um zu überprüfen, ob ein Dateiname existiert.  Wenn ein Dateiname vorhanden und nicht durch MIDL erstellt oder in anderer Form beschränkt ist, fordert die Funktion den Benutzer auf, den neuen Code mit der vorhandenen Datei zusammenzuführen.  
  
 Wenn der Dateiname nicht vorhanden und nicht beschränkt ist, wird die Datei mit dem angegebenen Namen erstellt.  
  
 Wenn der Dateiname von MIDL erstellt wird oder in anderer Form beschränkt ist, zeigt der Assistent eine Fehlermeldung an.  
  
## Beispiel  
  
```  
case "HTML_FILE":  
if (!HTML_FILE.disabled)  
   {  
   if (!window.external.FindSymbol("HTML_FILE_VALID"))  
      {  
      bValid = CanUseFileName(obj.value, false, true);  
      if (!bValid)  
      break;  
      window.external.AddSymbol("HTML_FILE_VALID", true)  
      }  
   }  
   bValid = window.external.ValidateFile(HTML_FILE.value, vsCMValidateFileExtHtml);  
   break;   
```  
  
## Siehe auch  
 [Anpassen von C\+\+\-Assistenten mit allgemeinen JScript\-Funktionen](../ide/customizing-cpp-wizards-with-common-jscript-functions.md)   
 [JScript\-Funktionen für C\+\+\-Assistenten](../ide/jscript-functions-for-cpp-wizards.md)   
 [Erstellen eines benutzerdefinierten Assistenten](../ide/creating-a-custom-wizard.md)   
 [Entwerfen eines Assistenten](../ide/designing-a-wizard.md)