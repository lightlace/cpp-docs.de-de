---
title: "Verwenden von Zuordnungen f&#252;r generischen Text | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "_UNICODE"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "_MBCS-Datentyp"
  - "_T-Typ"
  - "_TCHAR-Typ"
  - "_TEXT-Typ"
  - "_TINT-Typ"
  - "_TSCHAR-Typ"
  - "_TUCHAR-Typ"
  - "_TXCHAR-Typ"
  - "_UNICODE-Konstante"
  - "Datentypen für generischen Text"
  - "Allgemeintext-Zuordnungen"
  - "Zuordnungen, Generischer Text"
  - "MBCS-Datentyp"
  - "T-Typ"
  - "TCHAR-Typ"
  - "TCHAR.H-Datentypen, Zuordnungen definiert in"
  - "TEXT-Typ"
  - "TINT-Typ"
  - "TSCHAR-Typ"
  - "TUCHAR-Typ"
  - "TXCHAR-Typ"
  - "UNICODE-Konstante"
ms.assetid: 2848121c-e51f-4b9b-a2e6-833ece4b0cb3
caps.latest.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 8
---
# Verwenden von Zuordnungen f&#252;r generischen Text
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

**Microsoft\-spezifisch**  
  
 Um verschiedene Codeentwicklung für internationale Märkte vereinfachen, stellt die Microsoft\-Laufzeitbibliothek Zuordnungen des Microsoft\-Besondere" generischen Text für viele Datentypen, Routinen und andere Objekte.  Diese Zuordnungen sind in TCHAR.H. definiert.  Sie können diese Namenszuordnungen bereit verwenden, können Sie generischen Code schreiben, der für die drei Arten der verbleibenden Zeichensätze kompiliert werden kann: ASCII \(SBCS\), MBCS\- oder Unicode, abhängig von einer eindeutigen Konstante definieren Sie mithilfe einer `#define`\-Anweisung.  Zuordnungen für generischen Text sind Microsoft\-Erweiterungen, die zu nicht konformem ANSI sind.  
  
### Präprozessordirektiven zum Zuordnen von generischem Text  
  
|\#define|Kompilierte Version|Beispiel|  
|--------------|-------------------------|--------------|  
|`_UNICODE`|Unicode \(Breitzeichen\)|`_tcsrev` wird `_wcsrev` zugeordnet.|  
|`_MBCS`|Mehrbytezeichen|`_tcsrev` wird `_mbsrev` zugeordnet.|  
|Keine \(Standard: weder `_UNICODE` noch `_MBCS` definiert\)|SBCS \(ASCII\)|Zuordnungen zu `strrev``_tcsrev`|  
  
 Beispielsweise die Funktion `_tcsrev` für generischen Text, definiert in TCHAR.H, in den Zuordnungen zu `mbsrev`, wenn `MBCS` in einem Programm definiert wurde oder `_wcsrev` , wenn `_UNICODE`  definiert wurde.  Andernfalls `_tcsrev`  Zuordnungen zu `strrev`.  
  
 Der Datentyp `_TCHAR` des generischen Text, ebenfalls definiert in TCHAR.H, in den Zuordnungen, um `char` einzugeben, wenn `_MBCS` definiert ist, zu `wchar_t`, wenn `_UNICODE` definiert wird, und `char` einzugeben, wenn auch nicht Konstante definiert ist.  Andere Datentypzuordnungen werden in TCHAR.H weitere Datentypzuordnungen zur Verfügung gestellt, aber `_TCHAR` ist der Typ, der sehr nützlich ist.  
  
### Generische Textzuordnungen von Datentypen  
  
|Datentypname für generischen Text|\(\_UNICODE, SBCS \_MBCS nicht definiert\)|\_MBCS definiert|\_UNICODE definiert|  
|---------------------------------------|------------------------------------------------|----------------------|-------------------------|  
|`_TCHAR`|`char`|`char`|`wchar_t`|  
|`_TINT`|`int`|`int`|`wint_t`|  
|`_TSCHAR`|`signed char`|`signed char`|`wchar_t`|  
|`_TUCHAR`|`unsigned char`|`unsigned char`|`wchar_t`|  
|`_TXCHAR`|`char`|`unsigned char`|`wchar_t`|  
|`_T` oder `_TEXT`|Ohne Auswirkung \(wird vom Präprozessor entfernt\)|Ohne Auswirkung \(wird vom Präprozessor entfernt\)|`L` \(konvertiert, die Zeichen oder Zeichenfolge in die Unicode\-Entsprechung folgen\)|  
  
 Eine vollständige Liste mit generischen Textzuordnungen von Routinen, Variablen und anderen Objekten finden, [Zuordnungen für generischen Text](../c-runtime-library/generic-text-mappings.md).  
  
 Die folgenden Codefragmente veranschaulichen die Verwendung von `_TCHAR` und `_tcsrev` für die Zuordnung zu den MBCS\-, zu Unicode und TO der SBCS\-Modellen.  
  
```  
_TCHAR *RetVal, *szString;  
RetVal = _tcsrev(szString);  
```  
  
 Wenn `MBCS` definiert wurde, ordnet der Präprozessor dem vorangehenden Fragment dem folgenden Code:  
  
```  
char *RetVal, *szString;  
RetVal = _mbsrev(szString);  
```  
  
 Wenn `_UNICODE` definiert wurde, ordnet der Präprozessor dem gleichen Fragment dem folgenden Code:  
  
```  
wchar_t *RetVal, *szString;  
RetVal = _wcsrev(szString);  
```  
  
 Wenn weder `_MBCS` noch `_UNICODE` definiert wurde, ordnet der Präprozessor dem Einzelbyte\- ASCII\-Code zu, wie folgt:  
  
```  
char *RetVal, *szString;  
RetVal = strrev(szString);  
```  
  
 So können Sie eine einzige Quellcodedatei so schreiben, verwalten und kompilieren, dass sie mit Routinen ausgeführt, die zu einer der drei Zeichensätze ausgerichtet sind.  
  
 **END Microsoft\-spezifisch**  
  
## Siehe auch  
 [Zuordnungen für generischen Text](../c-runtime-library/generic-text-mappings.md)   
 [Datentypzuordnungen](../c-runtime-library/data-type-mappings.md)   
 [Zuordnungen von Konstanten und globalen Variablen](../c-runtime-library/constant-and-global-variable-mappings.md)   
 [Routinezuordnungen](../c-runtime-library/routine-mappings.md)   
 [Beispiel für ein Programm mit generischem Text](../c-runtime-library/a-sample-generic-text-program.md)