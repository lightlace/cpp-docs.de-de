---
title: strict_gs_check-Pragma
ms.date: 08/29/2019
f1_keywords:
- strict_gs_check
- strict_gs_check_CPP
helpviewer_keywords:
- strict_gs_check pragma
ms.assetid: decfec81-c916-42e0-a07f-8cc26df6a7ce
ms.openlocfilehash: 0b66e87f2280c923d05103fccfcbbc8d32daf3fd
ms.sourcegitcommit: 6e1c1822e7bcf3d2ef23eb8fac6465f88743facf
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/03/2019
ms.locfileid: "70216582"
---
# <a name="strict_gs_check-pragma"></a>strict_gs_check-Pragma

Dieses Pragma bietet eine verbesserte Sicherheitsüberprüfung.

## <a name="syntax"></a>Syntax

> **#pragma strict_gs_check (** [ **Push,** ] { **on** | **Off** } **)** \
> **#pragma strict_gs_check (Pop)**

## <a name="remarks"></a>Hinweise

Weist den Compiler an, einen zufällig ausgewählten Cookie im Funktionsstapel einzufügen, um verschiedene Kategorien eines stapelbasierten Pufferüberlaufs zu erkennen. Standardmäßig fügt die `/GS` Compileroption (Puffer Sicherheitsüberprüfung) kein Cookie für alle Funktionen ein. Weitere Informationen finden Sie unter [/GS (Puffer-Sicherheitsüberprüfung)](../build/reference/gs-buffer-security-check.md).

Kompilieren Sie mithilfe `/GS` von, um **strict_gs_check**zu aktivieren.

Verwenden Sie dieses Pragma in Codemodulen, die potenziell schädlichen Daten ausgesetzt sind. **strict_gs_check** ist ein aggressives Pragma, das auf Funktionen angewendet wird, die diese Verteidigung möglicherweise nicht benötigen, aber optimiert ist, um seine Auswirkung auf die Leistung der resultierenden Anwendung zu minimieren.

Auch wenn Sie das Pragma verwenden, sollten Sie sich bemühen, sicheren Code zu schreiben. Stellen Sie also sicher, dass im Code keine Pufferüberläufe ausgeführt werden. **strict_gs_check** schützt Ihre Anwendung möglicherweise vor Pufferüberläufen, die im Code verbleiben.

## <a name="example"></a>Beispiel

In diesem Beispiel tritt ein Pufferüberlauf auf, wenn ein Array in ein lokales Array kopiert wird. Wenn Sie diesen Code mit `/GS`kompilieren, wird kein Cookie in den Stapel eingefügt, da der Array Datentyp ein Zeiger ist. Durch das Hinzufügen des **strict_gs_check** -Pragmas wird das Stapel Cookie in den Funktions Stapel erzwingt.

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

[Pragma-Direktiven und das __Pragma-Schlüsselwort](../preprocessor/pragma-directives-and-the-pragma-keyword.md)\
[/GS (Puffer-Sicherheitsüberprüfung)](../build/reference/gs-buffer-security-check.md)
