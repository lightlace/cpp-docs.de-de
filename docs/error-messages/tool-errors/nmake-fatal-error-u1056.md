---
title: 'NMAKE: Schwerwiegender Fehler U1056'
ms.date: 11/04/2016
f1_keywords:
- U1056
helpviewer_keywords:
- U1056
ms.assetid: da855728-b69e-413c-83ed-df912126215e
ms.openlocfilehash: b15b14c04dd91ae648ea4311612c122f04f90477
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62367264"
---
# <a name="nmake-fatal-error-u1056"></a>NMAKE: Schwerwiegender Fehler U1056

Befehlsprozessor nicht gefunden werden.

Der Befehlsprozessor wies nicht den im angegebenen Pfad die **COMSPEC** oder **Pfad** Umgebungsvariablen.

NMAKE verwendet COMMAND.COM oder cmd ein. EXE-Datei als ein Befehlsprozessor, wenn Sie Befehle ausführen. Es sucht der Befehlsprozessor zuerst in den Pfad an, legen Sie in **COMSPEC**. Wenn **COMSPEC** ist nicht vorhanden, NMAKE-Suchvorgänge, die die Verzeichnisse im angegebenen **Pfad**.