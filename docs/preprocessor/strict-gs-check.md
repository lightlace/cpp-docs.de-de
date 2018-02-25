---
title: Strict_gs_check | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- strict_gs_check
- strict_gs_check_CPP
dev_langs:
- C++
helpviewer_keywords:
- strict_gs_check pragma
ms.assetid: decfec81-c916-42e0-a07f-8cc26df6a7ce
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 76b06f33626dfa237c81e6a23f343bb25ffb7c78
ms.sourcegitcommit: d51ed21ab2b434535f5c1d553b22e432073e1478
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/23/2018
---
# <a name="strictgscheck"></a>strict_gs_check
Dieses Pragma bietet eine verbesserte Sicherheitsüberprüfung.  
  
## <a name="syntax"></a>Syntax  
  
```  
#pragma strict_gs_check([push,] on )   
#pragma strict_gs_check([push,] off )   
#pragma strict_gs_check(pop)  
```  
  
## <a name="remarks"></a>Hinweise  
 Weist den Compiler an, einen zufällig ausgewählten Cookie im Funktionsstapel einzufügen, um verschiedene Kategorien eines stapelbasierten Pufferüberlaufs zu erkennen. Standardmäßig fügt die Compileroption /GS (Puffer-Sicherheitsüberprüfung) kein Cookie für alle Funktionen ein. Weitere Informationen finden Sie unter [/GS (Puffer-Sicherheitsüberprüfung)](../build/reference/gs-buffer-security-check.md).  
  
 Sie müssen mit /GS (Puffer-Sicherheitsüberprüfung) kompilieren, um strict_gs_check zu aktivieren.  
  
 Verwenden Sie dieses Pragma in Codemodulen, die potenziell schädlichen Daten ausgesetzt sind. Dieses Pragma ist sehr aggressiv und wird auf Funktionen angewendet, die einen solchen Schutz möglicherweise nicht benötigen. Es wird jedoch optimiert, um die Auswirkung auf die Leistung der resultierenden Anwendung zu minimieren.  
  
 Auch wenn Sie das Pragma verwenden, sollten Sie sich bemühen, sicheren Code zu schreiben. D. h., stellen Sie sicher, dass der Code keine Pufferüberläufe hat. Strict_gs_check kann Ihre Anwendung von Pufferüberläufe schützen, die im Code vorhanden.  
  
## <a name="example"></a>Beispiel  
 Im folgenden Code tritt ein Pufferüberlauf auf, wenn wir ein Array in ein lokales Array kopieren. Wenn Sie diesen Code mit /GS kompilieren, wird kein Cookie in den Stapel eingefügt, da der Arraydatentyp ein Zeiger ist. Durch Hinzufügen des strict_gs_check-Pragmas wird das Stapelcookie in den Funktionsstapel gezwungen.  
  
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
  
## <a name="see-also"></a>Siehe auch  
 [Pragma-Direktiven und das __Pragma-Schlüsselwort](../preprocessor/pragma-directives-and-the-pragma-keyword.md)   
 [/GS (Puffersicherheitsüberprüfung)](../build/reference/gs-buffer-security-check.md)