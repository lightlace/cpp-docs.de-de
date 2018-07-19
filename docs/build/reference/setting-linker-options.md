---
title: Festlegen von Linkeroptionen | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- files [C++], LINK
- input files [C++], linker
- linker [C++], ways to set options
- linker [C++], switches
- input files [C++]
- object/library modules
ms.assetid: e08fb487-0f2e-4f24-87db-232dbc8bd2e2
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 18728994be3f44152a263fb8a6009728e33a42a0
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
ms.locfileid: "32374920"
---
# <a name="setting-linker-options"></a>Festlegen von Linkeroptionen
Optionen des Linkers können innerhalb oder außerhalb der Entwicklungsumgebung festgelegt werden. Dieser Artikel für jedes (Linkeroption) behandelt, wie sie in der Entwicklungsumgebung eingestellt werden kann. Finden Sie unter [Optionen des Linkers](../../build/reference/linker-options.md) für eine vollständige Liste.  
  
 Wenn Sie den LINK außerhalb der Entwicklungsumgebung ausführen, können Sie die Eingabe in einer der folgenden Arten angeben:  
  
-   Auf der [über die Befehlszeile](../../build/reference/linker-command-line-syntax.md)  
  
-   Mithilfe von [Befehlsdateien](../../build/reference/link-command-files.md)  
  
-   In [Umgebungsvariablen](../../build/reference/link-environment-variables.md)  
  
 LINK-Optionen, erste Prozesse angegeben, in der Umgebungsvariablen LINK gefolgt von Optionen in der Reihenfolge, die sie in der Befehlszeile angegeben werden und in Befehlsdateien. Wenn eine Option mit anderen Argumenten wiederholt wird, hat das letzte Lesezeichen verarbeitet Vorrang vor.  
  
 Optionen gelten für den gesamten Build; keine Optionen können auf bestimmte Eingabedateien angewendet werden.  
  
## <a name="see-also"></a>Siehe auch  
 [Referenz zur C/C++-Erstellung](../../build/reference/c-cpp-building-reference.md)   
 [Linkeroptionen](../../build/reference/linker-options.md)