---
title: "Fehlerbehandlung in HTML-Assistentendateien"
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
  - "Fehlerbehandlung, Dateifehlerüberprüfung"
  - "HTML, Fehlerbehandlung"
ms.assetid: eb428a64-b681-4420-987d-92098bf98455
caps.latest.revision: 9
caps.handback.revision: "9"
ms.author: "mblome"
manager: "ghogen"
---
# Fehlerbehandlung in HTML-Assistentendateien
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Wenn Sie einen Assistenten mit Benutzeroberfläche erstellen, enthält das Projekt HTM\-Dateien.  Verwenden Sie diese Dateien, um das Projekt anzupassen.  Weitere Informationen finden Sie unter [HTML\-Dateien](../ide/html-files.md).  
  
 Das Projekt sollte eine Fehlerbehandlung umfassen.  Der folgende Code ist ein Beispiel für einen solchen Fehlerbehandlungscode.  
  
### So behandeln Sie Fehler in HTML  
  
1.  Wenn beim Überprüfen der Felder eine Validierungsmethode in einer DLL \(mit der die Fehlerinformationen festgelegt werden\) aufgerufen wird, muss `ReportError` ohne Parameter aufgerufen werden.  
  
    ```  
    function ValidateInput()  
    {  
       if (!window.external.ValidateFile(HEADER_FILE.value))  
       {  
          ReportError();  
          HEADER_FILE.focus();  
          return false;  
       }  
    }  
    ```  
  
2.  Wenn zum Überprüfen von Feldern lediglich das HTML\-Skript verwendet wird, rufen Sie zunächst `SetErrorInfo` und dann `ReportError` ohne Parameter auf.  
  
    ```  
    function OnWhatever()  
    {  
       if (!ValidateInput())  
          window.external.ReportErrror();  
       ....  
    }  
  
    function ValidateInput()  
    {  
       .....  
  
       if (HEADER_FILE.value == IMPL_FILE.value)  
       {  
          var L_ErrMsg_Text = "Header and implementation files cannot have the same name.";  
          SetErrorInfo(L_ErrMsg_Text);  
          bValid = false;  
       }  
       if (TYPE.value == "")  
       {  
          var L_ErrMsg4_Text = "Type cannot be blank.";  
          SetErrorInfo(L_ErrMsg4_Text);  
          bValid = false;  
       }  
       return bValid;  
    }  
    ```  
  
3.  Rufen Sie `ReportError` mit Parametern auf:  
  
    ```  
    function ValidateInput()  
    {  
       if (!IsListed(strType))  
       {  
          var L_Invalid2_Text = "The variable type should be one of the types listed.";  
          window.external.ReportError(L_Invalid2_Text);  
          VariableType.focus();  
          return false;  
       }  
    }  
    ```  
  
4.  Wenn Sie zu einem der Dialogfelder **Neues Projekt** oder **Neues Element hinzufügen** zurückkehren müssen, geben Sie **VS\_E\_WIZBACKBUTTONPRESS** zurück:  
  
    ```  
    try  
    {  
       oCM   = window.external.ProjectObject.CodeModel;  
    }  
    catch(e)  
    {  
       var L_NCBError_Text = "Cannot access the Class View information   
    file. Class View information will not be available.";  
       window.external.ReportError(L_NCBError_Text);  
       return VS_E_WIZARDBACKBUTTONPRESS;  
    ```  
  
## Siehe auch  
 [Für den Assistenten erstellte Dateien](../ide/files-created-for-your-wizard.md)   
 [Anpassen des Assistenten](../ide/customizing-your-wizard.md)