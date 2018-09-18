---
title: 'NMAKE: Schwerwiegender Fehler U1056 | Microsoft-Dokumentation'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- U1056
dev_langs:
- C++
helpviewer_keywords:
- U1056
ms.assetid: da855728-b69e-413c-83ed-df912126215e
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: e0a83c62bedf995708d5e99fee19f05696d05c2d
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/18/2018
ms.locfileid: "46065691"
---
# <a name="nmake-fatal-error-u1056"></a>NMAKE: Schwerwiegender Fehler U1056

Befehlsprozessor nicht gefunden werden.

Der Befehlsprozessor wies nicht den im angegebenen Pfad die **COMSPEC** oder **Pfad** Umgebungsvariablen.

NMAKE verwendet COMMAND.COM oder cmd ein. EXE-Datei als ein Befehlsprozessor, wenn Sie Befehle ausführen. Es sucht der Befehlsprozessor zuerst in den Pfad an, legen Sie in **COMSPEC**. Wenn **COMSPEC** ist nicht vorhanden, NMAKE-Suchvorgänge, die die Verzeichnisse im angegebenen **Pfad**.