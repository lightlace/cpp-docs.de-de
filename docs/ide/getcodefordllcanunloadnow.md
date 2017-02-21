---
title: "GetCodeForDllCanUnloadNow | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "GetCodeForDllCanUnloadNow"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "GetCodeForDllCanUnloadNow-Methode"
ms.assetid: 24ee3ef7-45be-4778-99e8-6df493f0782b
caps.latest.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 7
---
# GetCodeForDllCanUnloadNow
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Ruft den entsprechenden Code zum Entladen der DLL an.  
  
## <a name="syntax"></a>Syntax  
  
```  
  
      function GetCodeForDllCanUnloadNow(   
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
 Eine Zeichenfolge, die den Code zum Entladen der DLL.  
  
## <a name="remarks"></a>Hinweise  
 Rufen Sie diese Memberfunktion um den erforderlichen Code zum Entladen der DLL abzurufen. Das Aufrufen dieser Funktion erstellt eine einzelne Zeichenfolge durch die Verkettung der Array-Elemente, die Sie angeben.  
  
 Die folgende Tabelle zeigt Code für die DLL entladen wird.  
  
|Zeilennummer|Code|  
|-----------------|----------|  
|0|AFX_MANAGE_STATE(AfxGetStaticModuleState());|  
|1|Wenn (_AtlModule.GetLockCount() > 0)|  
|2|\treturn S_FALSE;|  
|3|S_OK zurück;|  
  
 Für jede der Zeilen zurückgegeben `GetCodeForDllCanUnloadNow` Fügt einen führenden Tabulator (`\t`) und ein abschließendes "CR-LF" (Wagenrücklauf - Zeilenvorschub) Zeichenpaar (`\r\n`).  
  
## <a name="example"></a>Beispiel  
  
```  
// Get the lines numbered 1 and 2 above  
GetCodeForDllCanUnloadNow(1, 2)  
  
// returns the following string  
// "\tif (_AtlModule.GetLockCount() > 0)\r\n\t\treturn S_FALSE;\r\n"  
  
```  
  
## <a name="see-also"></a>Siehe auch  
 [Anpassen von C++-Assistenten mit allgemeinen JScript-Funktionen](../ide/customizing-cpp-wizards-with-common-jscript-functions.md)   
 [JScript-Funktionen für C++-Assistenten](../ide/jscript-functions-for-cpp-wizards.md)   
 [Erstellen eines benutzerdefinierten Assistenten](../ide/creating-a-custom-wizard.md)   
 [Entwerfen eines Assistenten](../ide/designing-a-wizard.md)   
 [GetCodeForDllGetClassObject](../ide/getcodefordllgetclassobject.md)   
 [GetCodeForExitInstance](../ide/getcodeforexitinstance.md)