---
title: -FD (minimale Neuerstellung in der IDE) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- /FD
dev_langs:
- C++
helpviewer_keywords:
- /FD compiler option [C++]
- -FD compiler option [C++]
- FD compiler option [C++]
ms.assetid: 7ef21b8c-a448-4bb4-9585-a2a870028e17
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 74fb35ec25bed808e2165498c00b65723aba5bac
ms.sourcegitcommit: 92f2fff4ce77387b57a4546de1bd4bd464fb51b6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/17/2018
ms.locfileid: "45702441"
---
# <a name="fd-ide-minimal-rebuild"></a>/FD (Minimale Neuerstellung in der IDE)

**/ Fd** ist nicht verfügbar für Benutzer mit Ausnahme von in die [Befehlszeile](../../ide/command-line-property-pages.md) Eigenschaftenseite eines C++-Projekts **Eigenschaftenseiten** Dialogfeld, wenn und nur wenn  [ /GM (minimale Neuerstellung aktivieren)](../../build/reference/gm-enable-minimal-rebuild.md) nicht ebenfalls ausgewählt. **/ Fd** wirkt sich nicht nur aus der Entwicklungsumgebung. **/ Fd** ist nicht verfügbar gemacht, in der Ausgabe des **cl /?**.

Wenn Sie nicht aktivieren **/GM** in der Entwicklungsumgebung **/FD** verwendet werden. **/ Fd** wird sichergestellt, dass die .idb-Datei über ausreichende Informationen zu den Abhängigkeiten. **/ Fd** wird nur von der Entwicklungsumgebung verwendet und sollte nicht über die Befehlszeile oder ein Buildskript verwendet werden.

## <a name="see-also"></a>Siehe auch

[Ausgabedatei (/ F) Optionen](../../build/reference/output-file-f-options.md)
[Compileroptionen](../../build/reference/compiler-options.md)<br/>
[Festlegen von Compileroptionen](../../build/reference/setting-compiler-options.md)