---
title: Linkertoolfehler Lnk1561 | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- LNK1561
dev_langs:
- C++
helpviewer_keywords:
- LNK1561
ms.assetid: cb0b709b-7c9c-4496-8a4e-9e1e4aefe447
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: ac24ed0c4aff4cbd7f0ea95ff71d0b8c4b3be09c
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/18/2018
ms.locfileid: "46050761"
---
# <a name="linker-tools-error-lnk1561"></a>Linkertoolfehler LNK1561

Einstiegspunkt muss definiert werden

Der Linker wurde nicht gefunden. ein *Einstiegspunkt*, die erste Funktion in der ausführbaren Datei aufrufen. Wird standardmäßig der Linker sucht nach einer `main` oder `wmain` -Funktion für eine Konsolen-app, eine `WinMain` oder `wWinMain` -Funktion für eine Windows-app oder `DllMain` für eine DLL, die Initialisierung erforderlich ist. Sie können eine andere Funktion angeben, mit der [/Entry](../../build/reference/entry-entry-point-symbol.md) -Linkeroption.

Dieser Fehler kann mehrere Ursachen haben:
- Sie können nicht die Datei aufgenommen haben, die Ihr Einstiegspunkt in die Liste der Dateien auf den link definiert. Stellen Sie sicher, dass die Datei, die Einstiegspunktfunktion enthält, in Ihrer app verknüpft ist.
- Sie können den Einstiegspunkt, der mit der falschen Funktions-Signatur definiert haben, z. B. Sie möglicherweise haben falsch geschrieben ist die falsche Schreibweise für den Namen der Funktion verwendet oder der Rückgabetyp oder Parametertypen falsch angegeben.
- Sie können nicht angegeben haben die [/DLL](../../build/reference/dll-build-a-dll.md) option beim Erstellen einer DLL.
- Sie haben angegeben den Namen der Einstiegspunktfunktion nicht ordnungsgemäß bei der Verwendung der [/Entry](../../build/reference/entry-entry-point-symbol.md) -Linkeroption.
- Bei Verwendung der [LIB](../../build/reference/lib-reference.md) tool, um eine DLL erstellen, Sie haben eine DEF-Datei angegeben. Wenn dies der Fall ist, entfernen Sie die DEF-Datei aus dem Build.

Wenn eine app zu erstellen, sucht der Linker eine Einstiegspunktfunktion aufrufen, um Ihren Code zu starten. Dies ist die Funktion, die aufgerufen wird, nachdem die app geladen wird und die Laufzeit wird initialisiert. Sie müssen eine Einstiegspunktfunktion für eine app bereitstellen, oder Ihre app kann nicht ausgeführt werden. Ein Einstiegspunkt ist für eine DLL-Datei optional. Standardmäßig sucht der Linker eine Einstiegspunktfunktion, die bestimmten Namen und Signaturen, wie z. B. `int main(int, char**)`. Sie können einen anderen Funktionsnamen angeben, als Eintrag Punkt mithilfe der Linkeroption/Entry.

## <a name="example"></a>Beispiel

Im folgende Beispiel wird die LNK1561 generiert:

```cpp
// LNK1561.cpp
// LNK1561 expected
int i;
// add a main function to resolve this error
```