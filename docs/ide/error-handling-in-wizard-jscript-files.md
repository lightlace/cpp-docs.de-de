---
title: "Fehlerbehandlung in JScript-Assistentendateien | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Fehlerbehandlung, JScript"
  - "JScript, Fehlerbehandlung"
  - "JScript-Fehlerbehandlung bei Assistenten"
ms.assetid: 6df3ba46-7ab6-484c-ac45-b08f4b6a5900
caps.latest.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 8
---
# Fehlerbehandlung in JScript-Assistentendateien
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Wenn Sie einen Assistenten erstellen, enthält das Projekt die Dateien "Default.js" und "Common.js".  Verwenden Sie diese Dateien, um das Projekt anzupassen.  Weitere Informationen finden Sie unter [JScript\-Datei](../ide/jscript-file.md).  
  
 Das Projekt sollte eine Fehlerbehandlung umfassen.  Der folgende Code ist ein Beispiel für einen solchen Fehlerbehandlungscode.  
  
### So behandeln Sie Fehler in JScript  
  
1.  Um Fehler aufzufangen, wenn der Benutzer auf **Fertig stellen** klickt, geben Sie folgenden Code ein:  
  
    ```  
    function OnFinish(selProj, Class)  
    {  
       try  
       {  
          .....  
       }  
       catch(e)  
       {  
          if (e.description.length != 0)  
             SetErrorInfo(e.description, e.number);  
          return e.number  
       }  
    }  
    ```  
  
2.  `e` muss von allen Hilfsskriptfunktionen ausgelöst werden, die im Skript aufgerufen werden:  
  
    ```  
    function ExtenderFromType(strVariableType)  
    {  
       try  
       {  
          ....  
       }  
       catch(e)  
       {  
          throw e;  
       }  
    }  
    ```  
  
3.  Wenn der Parameter **PREPROCESS\_FUNCTION** in der [VSZ\-Datei](../ide/dot-vsz-file-project-control.md) enthalten ist, ruft der Assistent [CanAddATLClass](../ide/jscript-functions-for-cpp-wizards.md) auf.  Verwenden Sie im Falle eines Fehlers [SetErrorInfo](../ide/seterrorinfo.md), und geben Sie **false** zurück:  
  
    ```  
    function CanAddATLClass(oProj, oObject)  
    {  
       try  
       {  
          if (!IsATLProject(oProj))  
          {  
             if (!IsMFCProject(oProj, true))  
             {     
                var L_CanAddATLClass_Text = "ATL classes can only be added  
     to ATL, MFC EXE and MFC regular DLL projects.";  
                wizard.ReportError(L_CanAddATLClass_Text);  
                return false;  
             }  
             else  
             {  
                .....  
                var bRet = AddATLSupportToProject(oProj);  
                .....  
                return bRet;  
             }  
          }  
          return true;  
       }  
       catch(e)  
       {  
          throw e;  
       }  
    }  
    ```  
  
4.  Wenn Sie zu einem der Dialogfelder **Neues Projekt** oder **Neues Element hinzufügen** zurückkehren müssen, geben Sie **VS\_E\_WIZBACKBUTTONPRESS** zurück:  
  
    ```  
    function OnFinish(selProj, Class)  
    {  
       ....  
       if (!CheckAddtoProject(selProj))  
       {  
          return VS_E_WIZARDBACKBUTTONPRESS;  
       }  
    }  
    ```  
  
## Siehe auch  
 [Für den Assistenten erstellte Dateien](../ide/files-created-for-your-wizard.md)   
 [Anpassen des Assistenten](../ide/customizing-your-wizard.md)