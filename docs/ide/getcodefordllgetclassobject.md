---
title: "GetCodeForDllGetClassObject"
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
  - "GetCodeForDllGetClassObject"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "GetCodeForDllGetClassObject-Methode"
ms.assetid: 67b61b3b-9784-494f-ba01-17bffa9941ff
caps.latest.revision: 7
caps.handback.revision: "7"
ms.author: "mblome"
manager: "ghogen"
---
# GetCodeForDllGetClassObject
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Ruft den Code für das DLL-Klassenobjekt ab.  
  
## <a name="syntax"></a>Syntax  
  
```  
  
      function GetCodeForDllGetClassObject(   
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
 Eine Zeichenfolge, die den Code zum Abrufen des Klassenobjekts enthält.  
  
## <a name="remarks"></a>Hinweise  
 Rufen Sie diese Memberfunktion, um den Code für das Klassenobjekt abzurufen. Das Aufrufen dieser Funktion erstellt eine einzelne Zeichenfolge durch die Verkettung der Array-Elemente, die Sie angeben.  
  
 Die folgende Tabelle zeigt Code zum Abrufen des Codes für das Klassenobjekt:  
  
|Zeilennummer|Code|  
|-----------------|----------|  
|0|AFX_MANAGE_STATE(AfxGetStaticModuleState());|  
|1|Wenn (S_OK == _AtlModule.GetClassObject (Rclsid, Riid Ppv))|  
|2|\treturn S_OK;|  
|3|Zurückgeben von AfxDllGetClassObject (Rclsid, Riid, Ppv);|  
  
 Für jede der Zeilen zurückgegeben `GetCodeForDllGetClassObject` Fügt einen führenden Tabulator (`\t`) und ein abschließendes "CR-LF" (Wagenrücklauf - Zeilenvorschub) Zeichenpaar (`\r\n`).  
  
## <a name="example"></a>Beispiel  
  
```  
// Get the lines numbered 1 and 2 above  
GetCodeForDllGetClassObject(1, 2)  
  
// returns the following string  
// "\tif (S_OK == _AtlModule.GetClassObject(rclsid, riid, ppv))\r\n\t\treturn S_OK;\r\n"  
  
```  
  
## <a name="see-also"></a>Siehe auch  
 [Anpassen von C++-Assistenten mit allgemeinen JScript-Funktionen](../ide/customizing-cpp-wizards-with-common-jscript-functions.md)   
 [JScript-Funktionen für C++-Assistenten](../ide/jscript-functions-for-cpp-wizards.md)   
 [Erstellen eines benutzerdefinierten Assistenten](../ide/creating-a-custom-wizard.md)   
 [Entwerfen eines Assistenten](../ide/designing-a-wizard.md)