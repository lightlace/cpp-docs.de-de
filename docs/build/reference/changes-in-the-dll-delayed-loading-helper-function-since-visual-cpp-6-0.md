---
title: Änderungen in der DLL das verzögerte Laden von Hilfsfunktion seit Visual C++ 6.0 | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- delayed loading of DLLs, what's changed
- PFromRva method
- __delayLoadHelper2 function
- helper functions, what's changed
ms.assetid: 99f0be69-105d-49ba-8dd5-3be7939c0c72
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 0caf74f02b005ef65e8ac30750fdf244ddeeed0d
ms.sourcegitcommit: 92f2fff4ce77387b57a4546de1bd4bd464fb51b6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/17/2018
ms.locfileid: "45712269"
---
# <a name="changes-in-the-dll-delayed-loading-helper-function-since-visual-c-60"></a>Änderungen an der Hilfsfunktion für das verzögerte Laden von DLLs seit Visual C++ 6.0

Wenn Sie über mehrere Versionen von Visual C++ auf Ihrem Computer oder wenn Sie eine eigene Hilfsfunktion definiert haben, möglicherweise zu durch Problemen verzögerte Änderungen an der DLL an, laden die Hilfsfunktion. Zum Beispiel:

- **__delayLoadHelper** ist jetzt **__delayLoadHelper2**

- **__pfnDliNotifyHook** ist jetzt **__pfnDliNotifyHook2**

- **__pfnDliFailureHook** ist jetzt **__pfnDliFailureHook2**

- **__FUnloadDelayLoadedDLL** ist jetzt **__FUnloadDelayLoadedDLL2**

> [!NOTE]
>  Wenn Sie die Standard-Hilfsfunktion verwenden, werden diese Änderungen nicht betroffen. Es gibt keine Änderungen in Bezug auf, wie Sie den Linker aufrufen.

## <a name="multiple-versions-of-visual-c"></a>Mehrere Versionen von Visual C++

Wenn Sie mehrere Versionen von Visual C++ auf Ihrem Computer verfügen, stellen Sie sicher, dass der Linker "delayimp.lib" entspricht. Wenn ein Konflikt vorliegt, erhalten Sie einen Linkerfehler entweder `___delayLoadHelper2@8` oder `___delayLoadHelper@8` als ein nicht aufgelöstes externes Symbol. Dies bedeutet einen neuen Linker mit einer alten "delayimp.lib" ein, und die zweite bedeutet eine alte Linker mit einer neuen "delayimp.lib".

Wenn Sie einen nicht aufgelösten Linkerfehler erhalten, führen Sie [Dumpbin/linkermember](../../build/reference/linkermember.md): 1 auf die "delayimp.lib", die Sie erwarten, enthält die Hilfsfunktion, um festzustellen, welche Hilfsfunktion stattdessen definiert ist. Die Hilfsfunktion kann auch in einer Objektdatei definiert werden. Führen Sie [Dumpbin/Symbols](../../build/reference/symbols.md) und suchen Sie nach `delayLoadHelper(2)`.

Wenn Sie wissen, müssen Sie dann den Linker Visual C++ 6.0:

- Führen Sie auf der Hilfsfunktion für verzögertes Laden der LIB- oder OBJ-Datei zu bestimmen, ob er definiert Dumpbin **__delayLoadHelper2**. Wenn dies nicht der Fall ist, wird die Verknüpfung fehl.

- Definieren Sie **__delayLoadHelper** in die Verzögerung des Hilfsprogramms lib- oder OBJ-Datei zu laden.

## <a name="user-defined-helper-function"></a>Eine benutzerdefinierte Hilfsfunktion

Wenn Sie eine eigene Hilfsfunktion definiert und die aktuelle Version von Visual C++ verwenden, führen Sie folgende Schritte aus:

- Benennen Sie die Hilfsfunktion zum **__delayLoadHelper2**.

- Da der Zeiger in der Delay-Deskriptor (ImgDelayDescr in delayimp.h), relativen Adresse (RVA) funktioniert in beide 32- und 64-Bit-Programme wie erwartet von absoluten Adressen (VAs) geändert wurden, müssen Sie diese wieder in Zeiger konvertiert. Wurde eine neue Funktion eingeführt: PFromRva, finden Sie im delayhlp.cpp. Sie können diese Funktion auf jedes der Felder im Deskriptor verwenden, an beiden 32- oder 64-Bit-Zeiger konvertieren. Die Standard-Hilfsfunktion Verzögerung Laden ist weiterhin eine gute Vorlage zu verwenden als Beispiel.

## <a name="load-all-imports-for-a-delay-loaded-dll"></a>Laden Sie aller Importe für eine verzögert geladene DLL

Der Linker kann alle Importe aus einer DLL geladen werden, die Sie angegeben, um die verzögert geladen werden. Finden Sie unter [Laden aller Importe für eine verzögert geladene DLL](../../build/reference/loading-all-imports-for-a-delay-loaded-dll.md) für Weitere Informationen.

## <a name="see-also"></a>Siehe auch

[Die Hilfsfunktion](understanding-the-helper-function.md)