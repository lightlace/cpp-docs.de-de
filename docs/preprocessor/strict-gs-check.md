---
title: "strict_gs_check"
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
  - "strict_gs_check"
  - "strict_gs_check_CPP"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "strict_gs_check-Pragma"
ms.assetid: decfec81-c916-42e0-a07f-8cc26df6a7ce
caps.latest.revision: 9
caps.handback.revision: "9"
ms.author: "corob"
manager: "ghogen"
---
# strict_gs_check
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Dieses Pragma bietet eine verbesserte Sicherheitsüberprüfung.  
  
## Syntax  
  
```  
#pragma strict_gs_check([push,] on )   
#pragma strict_gs_check([push,] off )   
#pragma strict_gs_check(pop)  
```  
  
## Hinweise  
 Weist den Compiler an, einen zufällig ausgewählten Cookie im Funktionsstapel einzufügen, um verschiedene Kategorien eines stapelbasierten Pufferüberlaufs zu erkennen.  Standardmäßig fügt die Compileroption \/GS \(Puffer\-Sicherheitsüberprüfung\) kein Cookie für alle Funktionen ein.  Weitere Informationen finden Sie unter [\/GS \(Puffer\-Sicherheitsüberprüfung\)](../build/reference/gs-buffer-security-check.md).  
  
 Sie müssen mit \/GS \(Puffer\-Sicherheitsüberprüfung\) kompilieren, um strict\_gs\_check zu aktivieren.  
  
 Verwenden Sie dieses Pragma in Codemodulen, die potenziell schädlichen Daten ausgesetzt sind.  Dieses Pragma ist sehr aggressiv und wird auf Funktionen angewendet, die einen solchen Schutz möglicherweise nicht benötigen. Es wird jedoch optimiert, um die Auswirkung auf die Leistung der resultierenden Anwendung zu minimieren.  
  
 Auch wenn Sie das Pragma verwenden, sollten Sie sich bemühen, sicheren Code zu schreiben.  Überprüfen Sie daher, dass der Code keine Pufferüberläufe hat. strict\_gs\_check kann die Anwendung vor Pufferüberläufen schützen, die im Code verbleiben.  
  
## Beispiel  
 Im folgenden Code tritt ein Pufferüberlauf auf, wenn wir ein Array in ein lokales Array kopieren.  Wenn Sie diesen Code mit \/GS kompilieren, wird kein Cookie in den Stapel eingefügt, da der Arraydatentyp ein Zeiger ist.  Durch Hinzufügen des strict\_gs\_check\-Pragmas wird das Stapelcookie in den Funktionsstapel gezwungen.  
  
```cpp  
// pragma_strict_gs_check.cpp  
// compile with: /c  
  
#pragma strict_gs_check(on)  
  
void ** ReverseArray(void **pData,  
                     size_t cData)  
{  
    // *** This buffer is subject to being overrun!! ***  
    void *pReversed[20];  
  
    // Reverse the array into a temporary buffer  
    for (size_t j = 0, i = cData; i ; --i, ++j)  
        // *** Possible buffer overrun!! ***  
            pReversed[j] = pData[i];   
  
    // Copy temporary buffer back into input/output buffer  
    for (size_t i = 0; i < cData ; ++i)   
        pData[i] = pReversed[i];  
  
    return pData;  
}  
  
```  
  
## Siehe auch  
 [Pragma\-Direktiven und das \_\_Pragma\-Schlüsselwort](../preprocessor/pragma-directives-and-the-pragma-keyword.md)   
 [\/GS \(Puffer\-Sicherheitsüberprüfung\)](../build/reference/gs-buffer-security-check.md)