---
title: Erstellen von Text für die Inlinedatei
ms.date: 11/04/2016
helpviewer_keywords:
- inline files, creating text
- NMAKE program, inline files
- text, inline file
ms.assetid: b8a332ed-8244-4ff8-89e6-029d7f659725
ms.openlocfilehash: a45aa526ca99af93cda86a2a8e0580d4d036ca6d
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62272320"
---
# <a name="creating-inline-file-text"></a>Erstellen von Text für die Inlinedatei

Inline-Dateien sind temporär oder permanent.

## <a name="syntax"></a>Syntax

```
inlinetext
.
.
.
<<[KEEP | NOKEEP]
```

## <a name="remarks"></a>Hinweise

Geben Sie *Inlinetext* in der ersten Zeile nach dem Befehl. Markiert das Ende mit doppelten spitzen Klammern (<<) am Anfang einer separaten Zeile. Die Datei enthält alle *Inlinetext* vor den begrenzenden Klammern. Die *Inlinetext* makroerweiterungen und Ersetzungen, jedoch keine Richtlinien oder Makefile Kommentare haben. Leerzeichen, Tabulatoren und Zeilenumbruchzeichen werden als Literalzeichen behandelt.

Eine temporäre Datei für die Dauer der Sitzung vorhanden ist und von anderen Befehlen wiederverwendet werden kann. Geben Sie **behalten** nach der schließenden spitzen Klammern, dass die Datei nach der Sitzung NMAKE beibehalten wird eine unbenannte Datei auf dem Datenträger mit dem generierten Dateinamen beibehalten. Geben Sie **NOKEEP** oder nichts für eine temporäre Datei. **Behalten Sie** und **NOKEEP** sind nicht in der Groß-/Kleinschreibung beachtet.

## <a name="see-also"></a>Siehe auch

[Inlinedateien in einem Makefile](inline-files-in-a-makefile.md)
