---
title: "Verwenden von TCHAR.H-Datentypen mit _MBCS"
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
  - "_mbcs"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "_MBCS-Datentyp"
  - "MBCS-Datentyp"
  - "TCHAR.H-Datentypen"
ms.assetid: 48f471e7-9d2b-4a39-b841-16a0e15c0a18
caps.latest.revision: 8
caps.handback.revision: "8"
ms.author: "corob"
manager: "ghogen"
---
# Verwenden von TCHAR.H-Datentypen mit _MBCS
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

**Microsoft\-spezifisch**  
  
 Wie die Tabelle von Zuordnungs\- generischer Textroutinen \(siehe [Zuordnungen für generischen Text](../c-runtime-library/generic-text-mappings.md)\), angibt, wenn Manifest Konstante `_MBCS` definiert wird, eine angegebene Zuordnungen für generischen Text Routine zu einer der folgenden Routinen zugeordnet:  
  
-   einer SBCS\-Routine, die Mehrbyte\-Bytes, \-Zeichen und \-Zeichenfolgen in entsprechender Weise behandelt  In diesem Fall wird erwartet, dass die Zeichenfolgenargumente vom Typ `char*`.  Beispielsweise `_tprintf` Zuordnungen in `printf`; die Zeichenfolgenargumente für `printf` sind vom Typ `char*`.  Wenn Sie den Datentyp `_TCHAR` generischen Text für Zeichenfolgentypen verwenden, stimmen die formalen und tatsächlichen Parameter für `printf` Übereinstimmung da `_TCHAR*` Zuordnungen an `char*` ein.  
  
-   einer MBCS\-spezifischen Routine  In diesem Fall wird erwartet, dass die Zeichenfolgenargumente vom Typ `unsigned char*`.  Beispielsweise `_tcsrev`  Zuordnungen in `_mbsrev`, die eine Zeichenfolge vom Typ `unsigned char*` erwartet und zurückgibt.  Auch wenn Sie den Datentyp `_TCHAR`  generischen Text für Zeichenfolgentypen verwenden, unter Umständen ein Typkonflikt da `_TCHAR`  gibt, Zuordnungen, um `char` einzugeben.  
  
 Nachstehend finden Sie drei Lösungsvorschläge, mit denen dieser Typkonflikt \(sowie entsprechende Warnungen des C\-Compilers bzw. Fehlermeldungen des C\+\+\-Compilers\) verhindert werden können:  
  
-   Verwenden Sie das Standardverfahren.  TCHAR.H werden Prototypen generischer Textroutinen für die Routinen in den Laufzeitbibliotheken, wie im folgenden Beispiel.  
  
    ```  
    char *_tcsrev(char *);  
    ```  
  
     Im Standardfall wird der Prototyp für `_tcsrev` Zuordnungen zu `_mbsrev` über einen Thunk in LIBC.LIB.  Dadurch ändern sich die Typen der eingehenden Parameter von `_mbsrev` und des ausgehenden Rückgabewerts von `_TCHAR *` \(wie `char *`\) in `unsigned char *`.  Diese Methode stellt den Typübereinstimmung sichergestellt, wenn Sie `_TCHAR` verwenden, sie ist jedoch aufgrund der Verwendung relativ langsam.  
  
-   Verwenden Sie die Inlinefunktion, indem Sie folgende Präprozessoranweisung in den Code aufnehmen:  
  
    ```  
    #define _USE_INLINING  
    ```  
  
     Diese Methode wird ein Inlinefunktionsthunk, vorausgesetzt in TCHAR.H, um der Routine für generischen Text direkt der entsprechenden MBCS\-Routine zugeordnet.  Der folgende Codeauszug aus TCHAR.H enthält ein Beispiel dafür, wie dies durchgeführt wird.  
  
    ```  
    __inline char *_tcsrev(char *_s1)  
    {return (char *)_mbsrev((unsigned char *)_s1);}  
    ```  
  
     In den Fällen, in denen die Inlinefunktion verwendet werden kann, stellt dies die beste Lösung dar, da hierdurch die Typübereinstimmung sichergestellt wird und kein zusätzlicher Zeitaufwand erforderlich ist.  
  
-   Verwendung "direkte Zuordnung" indem Sie folgende Präprozessoranweisung in den Code.  
  
    ```  
    #define _MB_MAP_DIRECT  
    ```  
  
     Dieses Verfahren stellt eine schnelle Alternative dar, wenn Sie das Standardverfahren nicht verwenden möchten und Ihnen die Inlinefunktion nicht zur Verfügung steht.  Sie bewirkt die Routine für generischen Text, über ein Makro zugeordnet werden direkt der MBCS\-Version der Routine, wie im folgenden Beispiel aus TCHAR.H.  
  
    ```  
    #define _tcschr _mbschr  
    ```  
  
 Wenn Sie diesen Ansatz wählen, müssen Sie darauf achten, dass sichergestellt werden, dass den äquivalente Datentypen für die Argumente und Rückgabewerte von Zeichenfolgen verwendet werden.  Sie können angegebene Typumwandlung verwenden, um sicherzustellen, dass das richtige Typübereinstimmung Datentyp `_TXCHAR` oder mithilfe des generischen Text verwenden können.  `_TXCHAR` Zuordnungen, um `char` in SBCS\-Code Beibehaltung Zuordnungen, um `unsigned char` in MBCS\-Code einzugeben.  Weitere Informationen über generische Text, finden Sie unter [Zuordnungen für generischen Text](../c-runtime-library/generic-text-mappings.md).  
  
 **END Microsoft\-spezifisch**  
  
## Siehe auch  
 [Internationalisierung](../c-runtime-library/internationalization.md)   
 [Laufzeitroutinen nach Kategorie](../c-runtime-library/run-time-routines-by-category.md)