---
title: "GetCodeForDllRegisterServer"
ms.custom: na
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "article"
f1_keywords: 
  - "GetCodeForDllRegisterServer"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "GetCodeForDllRegisterServer-Methode"
ms.assetid: 2fe733ad-3f1e-4020-9ce3-68956da7d41d
caps.latest.revision: 7
caps.handback.revision: "7"
ms.author: "mblome"
manager: "ghogen"
---
# GetCodeForDllRegisterServer
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Ruft den entsprechenden Code zum Registrieren eines Servers ab.  
  
## <a name="syntax"></a>Syntax  
  
```  
  
      function GetCodeForDllRegisterServer(   
   nLineStart,   
   nLineEnd    
);  
```  
  
#### <a name="parameters"></a>Parameter  
 `nLineStart`  
 Die nullbasierte Zeilennummer für den Start der Funktion.  
  
 `nLineEnd`  
 Die nullbasierte Zeilennummer für das Ende der Funktion.  
  
## <a name="return-value"></a>Rückgabewert  
 Eine Zeichenfolge, die den Code zum Registrieren des Servers  
  
## <a name="remarks"></a>Hinweise  
 Rufen Sie diese Memberfunktion um den erforderlichen Code zum Registrieren eines Servers abzurufen:  
  
|Zeilennummer|Code|  
|-----------------|----------|  
|0|AFX_MANAGE_STATE(AfxGetStaticModuleState());|  
|1|_AtlModule.UpdateRegistryAppId(true);|  
|2|HRESULT ' hres ' = _AtlModule.RegisterServer(TRUE);|  
|3|Wenn (' hres '! = S_OK)|  
|4|\treturn ' hres ';|  
|5|If (!) COleObjectFactory::UpdateRegistryAll(TRUE))|  
|6|\treturn ResultFromScode(SELFREG_E_CLASS);|  
|7|S_OK zurück;|  
  
 Für jede der Zeilen zurückgegeben `GetCodeForDllRegisterServer` Fügt einen führenden Tabulator (`\t`) und ein abschließendes "CR-LF" (Wagenrücklauf - Zeilenvorschub) Zeichenpaar (`\r\n`).  
  
## <a name="example"></a>Beispiel  
  
```  
// Get the lines numbered 2 and 3 above  
GetCodeForDllRegisterServer(2, 3)  
  
// returns the following string  
// "\tHRESULT hRes = _AtlModule.RegisterServer(TRUE);\r\n\tif (hRes != S_OK)\r\n"  
  
```  
  
## <a name="see-also"></a>Siehe auch  
 [Anpassen von C++-Assistenten mit allgemeinen JScript-Funktionen](../ide/customizing-cpp-wizards-with-common-jscript-functions.md)   
 [JScript-Funktionen für C++-Assistenten](../ide/jscript-functions-for-cpp-wizards.md)   
 [Erstellen eines benutzerdefinierten Assistenten](../ide/creating-a-custom-wizard.md)   
 [Entwerfen eines Assistenten](../ide/designing-a-wizard.md)   
 [GetCodeForDllUnregisterServer](../ide/getcodefordllunregisterserver.md)