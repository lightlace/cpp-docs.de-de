---
title: "GetCodeForExitInstance | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "GetCodeForExitInstance"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "GetCodeForExitInstance-Methode"
ms.assetid: 41fe3d79-a1f4-4bb5-b3f5-7859e255b4e7
caps.latest.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 7
---
# GetCodeForExitInstance
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Ruft die [ExitInstance](../Topic/CWinApp::ExitInstance.md) Code für den Assistenten beendet.  
  
## <a name="syntax"></a>Syntax  
  
```  
  
      function GetCodeForExitInstance(   
   nLineStart,   
   nLineEnd    
)   
```  
  
#### <a name="parameters"></a>Parameter  
 `nLineStart`  
 Die nullbasierte Zeilennummer für den Start der Funktion.  
  
 `nLineEnd`  
 Die nullbasierte Zeilennummer für das Ende der Funktion.  
  
## <a name="return-value"></a>Rückgabewert  
 Eine Zeichenfolge, die den Code zum Beenden der Assistenteninstanz enthält.  
  
## <a name="remarks"></a>Hinweise  
 Rufen Sie diese Memberfunktion um den erforderlichen Code zum Beenden einer Instanz des Assistenten abzurufen:  
  
|Zeilennummer|ExitInstance-code|  
|-----------------|-----------------------|  
|0|_AtlModule.RevokeClassObjects();|  
|1|Geben Sie CWinApp::ExitInstance() zurück.|  
  
 Für jede der Zeilen zurückgegeben `GetCodeForExitInstance` Fügt einen führenden Tabulator (`\t`) und ein abschließendes "CR-LF" (Wagenrücklauf - Zeilenvorschub) Zeichenpaar (`\r\n`).  
  
## <a name="example"></a>Beispiel  
  
```  
if (!oExitInstance)  
   {  
      oExitInstance = oCWinApp.AddFunction("ExitInstance",   
      vsCMFunctionFunction, "BOOL", vsCMAddPositionEnd, vsCMAccessPublic,   
      strProjectCPP);  
      oExitInstance.BodyText = GetCodeForExitInstance(0, 1);  
   }  
// returns the following string  
// "\t_AtlModule.RevokeClassObjects();\r\n  
// \treturn CWinApp::ExitInstance();\r\n"  
else  
   {  
   oExitInstance.StartPointOf(vsCMPartBody,   
   vsCMWhereDefinition).CreateEditPoint().Insert(GetCodeForExitInstance(0,   
   0));  
// returns the following string  
// "\t_AtlModule.RevokeClassObjects();\r\n  
      oCM.Synchronize();  
   }  
  
```  
  
## <a name="see-also"></a>Siehe auch  
 [Anpassen von C++-Assistenten mit allgemeinen JScript-Funktionen](../ide/customizing-cpp-wizards-with-common-jscript-functions.md)   
 [JScript-Funktionen für C++-Assistenten](../ide/jscript-functions-for-cpp-wizards.md)   
 [Erstellen eines benutzerdefinierten Assistenten](../ide/creating-a-custom-wizard.md)   
 [Entwerfen eines Assistenten](../ide/designing-a-wizard.md)   
 [GetCodeForDllCanUnloadNow](../ide/getcodefordllcanunloadnow.md)   
 [GetCodeForInitInstance](../ide/getcodeforinitinstance.md)