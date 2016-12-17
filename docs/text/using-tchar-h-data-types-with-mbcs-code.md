---
title: "Verwenden von TCHAR.H-Datentypen in _MBCS-Code"
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
  - ""tchar.h""
  - "TCHAR"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Allgemeintext-Datentypen [C++]"
  - "Allgemeintext-Zuordnungen [C++]"
  - "Zuordnen von Allgemeintext"
  - "Zuordnungen [C++], TCHAR.H"
  - "MBCS [C++], Allgemeintext-Zuordnungen"
  - "TCHAR.H-Datentypen, Zuordnen"
ms.assetid: 298583c5-22c3-40f6-920e-9ec96d42abd8
caps.latest.revision: 7
caps.handback.revision: "7"
ms.author: "ghogen"
manager: "ghogen"
---
# Verwenden von TCHAR.H-Datentypen in _MBCS-Code
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Wenn die eindeutige **\_MBCS**\-Konstante definiert ist, wird eine bestimmte generische Textroutine einer der folgenden Routinen zugeordnet:  
  
-   einer SBCS\-Routine, die Mehrbyte\-Bytes, \-Zeichen und \-Zeichenfolgen in entsprechender Weise behandelt  In diesem Fall wird erwartet, dass die Zeichenfolgenargumente vom Typ **char\*** sind.  `_tprintf` wird z. B. der `printf`\-Funktion zugeordnet; die Zeichenfolgenargumente für `printf` sind vom Typ **char\***.  Wenn Sie den generischen Textdatentyp **\_TCHAR** für Zeichenfolgentypen verwenden, stimmen die formalen und tatsächlichen Parametertypen für `printf` überein, da **\_TCHAR**\* dem Typ **char\*** zugeordnet wird.  
  
-   einer MBCS\-spezifischen Routine  In diesem Fall wird erwartet, dass die Zeichenfolgenargumente vom Typ **unsigned char\*** sind.  `_tcsrev` wird z. B. der Funktion `_mbsrev` zugeordnet, die eine Zeichenfolge vom Typ `unsigned` **char\*** erwartet und zurückgibt.  Wenn Sie den generischen Textdatentyp **\_TCHAR** für Zeichenfolgentypen verwenden, tritt unter Umständen ein Typkonflikt ein, da **\_TCHAR** dem Typ `char` zugeordnet wird.  
  
 Nachstehend finden Sie drei Lösungsvorschläge, mit denen dieser Typkonflikt \(sowie entsprechende Warnungen des C\-Compilers bzw. Fehlermeldungen des C\+\+\-Compilers\) verhindert werden können:  
  
-   Verwenden Sie das Standardverfahren.  Von Tchar.h werden Prototypen generischer Textroutinen für die Routinen in den Laufzeitbibliotheken zur Verfügung gestellt, wie im folgenden Beispiel dargestellt:  
  
    ```  
    char * _tcsrev(char *);  
    ```  
  
     Im Standardfall wird der Prototyp für `_tcsrev` der Funktion `_mbsrev` über einen Thunk in Libc.lib zugeordnet.  Dadurch ändern sich die Typen der eingehenden Parameter von `_mbsrev` und des ausgehenden Rückgabewerts von **\_TCHAR \*** \(also `char` **\***\) in `unsigned` `char` **\***.  Mit dieser Methode wird bei Verwendung von **\_TCHAR** die Typübereinstimmung sichergestellt; sie ist jedoch aufgrund der zahlreichen Funktionsaufrufe verhältnismäßig langsam.  
  
-   Verwenden Sie die Inlinefunktion, indem Sie folgende Präprozessoranweisung in den Code aufnehmen:  
  
    ```  
    #define _USE_INLINING  
    ```  
  
     Durch diese Methode wird von einem in Tchar.h zur Verfügung gestellten Inlinefunktions\-Thunk die generische Textroutine direkt der entsprechenden MBCS\-Routine zugeordnet.  Aus folgendem Codeauszug aus TCHAR.H geht hervor, wie dies vonstatten geht:  
  
    ```  
    __inline char *_tcsrev(char *_s1)  
    {return (char *)_mbsrev((unsigned char *)_s1);}  
    ```  
  
     In den Fällen, in denen die Inlinefunktion verwendet werden kann, stellt dies die beste Lösung dar, da hierdurch die Typübereinstimmung sichergestellt wird und kein zusätzlicher Zeitaufwand erforderlich ist.  
  
-   Verwenden Sie die direkte Zuordnung, indem Sie folgende Präprozessoranweisung in den Code aufnehmen:  
  
    ```  
    #define _MB_MAP_DIRECT  
    ```  
  
     Dieses Verfahren stellt eine schnelle Alternative dar, wenn Sie das Standardverfahren nicht verwenden möchten und Ihnen die Inlinefunktion nicht zur Verfügung steht.  Hierbei wird die generische Textroutine über ein Makro direkt der MBCS\-Version der Routine zugeordnet, wie im folgenden Beispiel aus Tchar.h dargestellt:  
  
    ```  
    #define _tcschr _mbschr  
    ```  
  
     Wenn Sie dieses Verfahren bevorzugen, müssen Sie unbedingt sicherstellen, dass geeignete Datentypen für die Argumente und Rückgabewerte von Zeichenfolgen verwendet werden.  Sie können die Typübereinstimmung durch Typumwandlung oder mithilfe des generischen Textdatentyps **\_TXCHAR** sicherstellen.  In SBCS\-Code wird **\_TXCHAR** dem Typ **char** zugeordnet. In MBCS\-Code wird **\_TXCHAR** dem Typ `unsigned` `char` zugeordnet.  Weitere Informationen über generische Textmakros finden Sie unter [Zuordnungen für generischen Text](../c-runtime-library/generic-text-mappings.md) in der *Laufzeitbibliotheksreferenz*.  
  
## Siehe auch  
 [Zuordnungen für generischen Text in Tchar.h](../text/generic-text-mappings-in-tchar-h.md)