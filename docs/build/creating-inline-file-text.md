---
title: Erstellen von Text für die Inlinedatei | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- inline files, creating text
- NMAKE program, inline files
- text, inline file
ms.assetid: b8a332ed-8244-4ff8-89e6-029d7f659725
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: ce0a345c6c2f48d3d5c2e6fb9d9cfc2a5c03e4ed
ms.sourcegitcommit: 92f2fff4ce77387b57a4546de1bd4bd464fb51b6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/17/2018
ms.locfileid: "45720914"
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

[Inlinedateien in einem Makefile](../build/inline-files-in-a-makefile.md)