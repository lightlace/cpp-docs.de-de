---
title: "Datentypzuordnungen | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "_TXCHAR"
  - "_TUCHAR"
  - "_TINT"
  - "_TSCHAR"
  - "_TCHAR"
  - "TCHAR::H"
  - "TCHAR"
  - "_T"
  - "_TEXT"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "_T-Typ"
  - "_TCHAR-Typ"
  - "_TEXT-Typ"
  - "_TINT-Typ"
  - "_TSCHAR-Typ"
  - "_TUCHAR-Typ"
  - "_TXCHAR-Typ"
  - "Datentypen für generischen Text"
  - "T-Typ"
  - "TCHAR-Typ"
  - "TCHAR.H-Datentypen, Zuordnungen definiert in"
  - "TEXT-Typ"
  - "TINT-Typ"
  - "TSCHAR-Typ"
  - "TUCHAR-Typ"
  - "TXCHAR-Typ"
ms.assetid: 4e573c05-8800-468b-ae5f-76ff7409835e
caps.latest.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 7
---
# Datentypzuordnungen
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Diese Datentypzuordnungen werden in TCHAR.H definiert und abhängen an, ob Konstante `_UNICODE` oder `_MBCS` in einem Programm definiert wurde.  
  
 Weitere Informationen finden Sie unter [Verwenden TCHAR.H\-Datentypen \_MBCS mit Code](../text/using-tchar-h-data-types-with-mbcs-code.md).  
  
### Generische Textzuordnungen von Datentypen  
  
|Generischer Text<br /><br /> Datentypname|\(\_UNICODE, SBCS<br /><br /> \_MBCS nicht<br /><br /> definiert\)|\_MBCS<br /><br /> Definition|\_UNICODE<br /><br /> Definition|  
|---------------------------------------|--------------------------------------------------------|---------------------------|------------------------------|  
|`_TCHAR`|`char`|`char`|`wchar_t`|  
|`_tfinddata_t`|`_finddata_t`|`_finddata_t`|`_wfinddata_t`|  
|`_tfinddata64_t`|`__finddata64_t`|`__finddata64_t`|`__wfinddata64_t`|  
|`_tfinddatai64_t`|`_finddatai64_t`|`_finddatai64_t`|`_wfinddatai64_t`|  
|`_TINT`|`int`|`int`|`wint_t`|  
|`_TSCHAR`|`signed char`|`signed char`|`wchar_t`|  
|`_TUCHAR`|`unsigned char`|`unsigned char`|`wchar_t`|  
|`_TXCHAR`|`char`|`unsigned char`|`wchar_t`|  
|`_T` oder `_TEXT`|Ohne Auswirkung \(wird vom Präprozessor entfernt\)|Ohne Auswirkung \(wird vom Präprozessor entfernt\)|`L` \(konvertiert, die Zeichen oder Zeichenfolge in die Unicode\-Entsprechung folgen\)|  
  
## Siehe auch  
 [Zuordnungen für generischen Text](../c-runtime-library/generic-text-mappings.md)   
 [Zuordnungen von Konstanten und globalen Variablen](../c-runtime-library/constant-and-global-variable-mappings.md)   
 [Routinezuordnungen](../c-runtime-library/routine-mappings.md)   
 [Beispiel für ein Programm mit generischem Text](../c-runtime-library/a-sample-generic-text-program.md)   
 [Verwenden von Zuordnungen für generischen Text](../c-runtime-library/using-generic-text-mappings.md)