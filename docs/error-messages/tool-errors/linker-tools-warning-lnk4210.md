---
title: Linkertoolwarnung LNK4210
ms.date: 11/04/2016
f1_keywords:
- LNK4210
helpviewer_keywords:
- LNK4210
ms.assetid: db48cff8-a2be-4a77-8d03-552b42c228fa
ms.openlocfilehash: 75376129ce0033c717a4da3074cee9de132d357d
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62395065"
---
# <a name="linker-tools-warning-lnk4210"></a>Linkertoolwarnung LNK4210

> Abschnitt *Abschnitt* vorhanden ist, gibt es unter Umständen werden unbehandelte statische Initialisierer oder Terminatoren

## <a name="remarks"></a>Hinweise

Code wurde eingeführt, statische Initialisierer oder Terminatoren, aber die VCRuntime-Bibliothek-Startcode oder dessen Entsprechung (die die statische Initialisierer oder Terminatoren ausgeführt werden muss) wird nicht ausgeführt werden, beim Starten der Anwendung. Hier sind einige Beispiele für Code, der statische Initialisierer oder Terminatoren erfordert:

- Globale Class-Variable mit einem Konstruktor, Destruktor, oder virtuelle Funktionstabelle.

- Globale Variable, die mit einer nicht-Kompilierzeitkonstante initialisiert werden.

Um dieses Problem zu beheben, versuchen Sie Folgendes:

- Entfernen Sie sämtlichen Code, mit der statischen Initialisierer.

- Verwenden Sie keine [/NOENTRY](../../build/reference/noentry-no-entry-point.md). Nach Sie/NOENTRY entfernen, müssen Sie möglicherweise auch entfernen [/NODEFAULTLIB](../../build/reference/nodefaultlib-ignore-libraries.md) der Linker-Befehlszeile.

- Wenn Ihr Build "/ MT" verwendet, fügen Sie "LIBCMT.lib", "libvcruntime.lib" und "libucrt.lib", auf die Linker-Befehlszeile. Wenn Ihr Build/MTd verwendet, fügen Sie "LIBCMTD.lib" und "vcruntimed.lib" libucrtd.lib aus.

- Beim Wechsel von/CLR: pure-Kompilierung zu/CLR, entfernen die [/Entry](../../build/reference/entry-entry-point-symbol.md) Option in der Linker-Befehlszeile. Dies ermöglicht CRT-Initialisierung und statische Initialisierer, die beim Start der Anwendung ausgeführt werden. Die **/CLR: pure** Compileroption ist in Visual Studio 2015 als veraltet markiert und in Visual Studio 2017 nicht unterstützt.

Die [/GS](../../build/reference/gs-buffer-security-check.md) -Compileroption erfordert Initialisierung durch die `__security_init_cookie` Funktion. Diese Initialisierung erfolgt in den Startcode VCRuntime-Bibliothek, die ausgeführt, in wird der Standardeinstellung `_DllMainCRTStartup`.

- Wenn Ihr Projekt erstellt wird mit/Entry und/Entry anders als eine Funktion übergeben wird `_DllMainCRTStartup`, muss die Funktion aufrufen `_CRT_INIT` CRT initialisiert werden. Dieser Aufruf allein reicht nicht, wenn die DLL/GS verwendet, statische Initialisierer erfordert oder im Kontext der MFC oder ATL-Code aufgerufen wird. Finden Sie unter [DLLs und Visual C++-Laufzeitbibliothek Verhalten](../../build/run-time-library-behavior.md) für Weitere Informationen.

## <a name="see-also"></a>Siehe auch

- [Festlegen von Linkeroptionen](../../build/reference/linking.md)
