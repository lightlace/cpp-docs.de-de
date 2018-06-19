---
title: Änderungen an der das verzögerte Laden von Hilfsfunktion seit Visual C++ 6.0 | Microsoft Docs
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
ms.openlocfilehash: 3af68e5ba92a96502e295e75520cd182b4633dae
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
ms.locfileid: "32371852"
---
# <a name="changes-in-the-dll-delayed-loading-helper-function-since-visual-c-60"></a>Änderungen an der Hilfsfunktion für das verzögerte Laden von DLLs seit Visual C++ 6.0
Wenn Sie mehrere Versionen von Visual C++ auf Ihrem Computer haben oder wenn Sie eine eigene Hilfsfunktion definiert haben, es möglicherweise von kommt verzögert Änderungen an der DLL laden Hilfsfunktion. Zum Beispiel:  
  
-   **__delayLoadHelper** ist jetzt **__delayLoadHelper2**  
  
-   **__pfnDliNotifyHook** ist jetzt **__pfnDliNotifyHook2**  
  
-   **__pfnDliFailureHook** ist jetzt **__pfnDliFailureHook2**  
  
-   **__FUnloadDelayLoadedDLL** ist jetzt **__FUnloadDelayLoadedDLL2**  
  
> [!NOTE]
>  Wenn Sie die Standard-Hilfsfunktion verwenden, werden diese Änderungen nicht betroffen. Es sind keine Änderungen bezüglich wie den Linker aufrufen.  
  
## <a name="multiple-versions-of-visual-c"></a>Mehrere Versionen von Visual C++  
 Wenn Sie mehrere Versionen von Visual C++ auf Ihrem Computer verfügen, stellen Sie sicher, dass der Linker "delayimp.lib" übereinstimmt. Wenn es ein Konflikt besteht, erhalten Sie einen Linkerfehler entweder `___delayLoadHelper2@8` oder `___delayLoadHelper@8` als ein nicht aufgelöstes externes Symbol. Dies bedeutet eine neue Verknüpfung mit einer alten "delayimp.lib" und letztere impliziert einen alten Linker mit einer neuen "delayimp.lib".  
  
 Führen Sie eine nicht aufgelöste Linkerfehler [Dumpbin/linkermember](../../build/reference/linkermember.md): 1 für die "delayimp.lib", die Sie erwarten, enthalten die Hilfsfunktion, um festzustellen, welche Hilfsfunktion stattdessen definiert ist. Die Hilfsfunktion kann auch in einer Objektdatei definiert werden; Führen Sie [Dumpbin/Symbols](../../build/reference/symbols.md) und suchen Sie nach `delayLoadHelper(2)`.  
  
 Wenn Sie wissen müssen Sie dann den Linker Visual C++ 6.0:  
  
-   Ausführen von Dumpbin für Verzögerung Hilfsfunktion für das Laden des lib- oder OBJ-Datei, um zu bestimmen, ob es definiert **__delayLoadHelper2**. Wenn dies nicht der Fall ist, wird die Verknüpfung fehl.  
  
-   Definieren Sie **__delayLoadHelper** in die Verzögerung der Hilfsfunktion lib- oder OBJ-Datei zu laden.  
  
## <a name="user-defined-helper-function"></a>Benutzerdefinierte Hilfsfunktion  
 Wenn Sie eine eigene Hilfsfunktion definiert und die aktuelle Version von Visual C++ verwenden, führen Sie folgende Schritte aus:  
  
-   Benennen Sie die Hilfsfunktion auf **__delayLoadHelper2**.  
  
-   Da die Zeiger im Verzögerungsdeskriptor (ImgDelayDescr in delayimp.h) von absoluten Adressen (VAs) zu relativen Adressen (RVA) in beide 32- und 64-Bit-Programme wie erwartet funktioniert geändert wurden, müssen Sie diese wieder in Zeiger konvertiert. Es wurde eine neue Funktion eingeführt: PFromRva, in delayhlp.cpp gefunden. Diese Funktion können auf jedes der Felder im Deskriptor Sie um sie wieder auf entweder 32 oder 64-Bit-Zeiger zu konvertieren. Die Hilfsfunktion Standard verzögertes Laden wird weiterhin eine gute Vorlage als Beispiel verwendet werden.  
  
## <a name="load-all-imports-for-a-delay-loaded-dll"></a>Laden Sie aller Importe für eine verzögert geladene DLL  
 Der Linker kann alle Importe aus einer DLL laden, die Sie angegeben haben, um die Verzögerung geladen werden. Finden Sie unter [Laden aller Importe für eine verzögert geladene DLL](../../build/reference/loading-all-imports-for-a-delay-loaded-dll.md) für Weitere Informationen.  
  
## <a name="see-also"></a>Siehe auch  
 [Die Hilfsfunktion](understanding-the-helper-function.md)