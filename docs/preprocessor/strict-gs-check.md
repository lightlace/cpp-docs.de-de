---
title: strict_gs_check
ms.date: 11/04/2016
f1_keywords:
- strict_gs_check
- strict_gs_check_CPP
helpviewer_keywords:
- strict_gs_check pragma
ms.assetid: decfec81-c916-42e0-a07f-8cc26df6a7ce
ms.openlocfilehash: b62e1be466e65c0de6fb4eaa33ac6e99915529e6
ms.sourcegitcommit: 72583d30170d6ef29ea5c6848dc00169f2c909aa
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59037803"
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

Weist den Compiler an, einen zufällig ausgewählten Cookie im Funktionsstapel einzufügen, um verschiedene Kategorien eines stapelbasierten Pufferüberlaufs zu erkennen. In der Standardeinstellung die `/GS` -Compileroption (Puffer-Sicherheitsüberprüfung) ist ein Cookie für alle Funktionen nicht eingefügt werden. Weitere Informationen finden Sie unter [/GS (Puffer-Sicherheitsüberprüfung)](../build/reference/gs-buffer-security-check.md).

Muss der Kompilierung mit `/GS` (Puffer-Sicherheitsüberprüfung) aktivieren **Strict_gs_check**.

Verwenden Sie dieses Pragma in Codemodulen, die potenziell schädlichen Daten ausgesetzt sind. Dieses Pragma ist sehr aggressiv und wird auf Funktionen angewendet, die einen solchen Schutz möglicherweise nicht benötigen. Es wird jedoch optimiert, um die Auswirkung auf die Leistung der resultierenden Anwendung zu minimieren.

Auch wenn Sie das Pragma verwenden, sollten Sie sich bemühen, sicheren Code zu schreiben. Das heißt, stellen Sie sicher, dass Ihr Code keine Pufferüberläufe hat. **Strict_gs_check** schützen Sie Ihre Anwendung vor Pufferüberläufen, die in Ihrem Code bleiben kann.

## <a name="example"></a>Beispiel

Im folgenden Code tritt ein Pufferüberlauf auf, wenn wir ein Array in ein lokales Array kopieren. Beim Kompilieren dieses Codes mit `/GS`, kein Cookie wird im Stapel eingefügt, da der Arraydatentyp ein Zeiger ist. Hinzufügen der **Strict_gs_check** Pragma wird das stapelcookie in den funktionsstapel erzwungen.

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

[Pragma-Direktiven und das __Pragma-Schlüsselwort](../preprocessor/pragma-directives-and-the-pragma-keyword.md)<br/>
[/GS (Puffersicherheitsüberprüfung)](../build/reference/gs-buffer-security-check.md)