---
title: Angeben einer Inlinedatei | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- NMAKE program, inline files
- inline files [C++], specifying NMAKE
- files [C++], inline
ms.assetid: 393eccfb-3fc9-4bac-a30c-8ac8d221cca3
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 73983094f10088920100b4fbbb8d870aee13f05e
ms.sourcegitcommit: 92f2fff4ce77387b57a4546de1bd4bd464fb51b6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/17/2018
ms.locfileid: "45720563"
---
# <a name="specifying-an-inline-file"></a>Angeben einer Inlinedatei

Geben Sie zwei spitzen Klammern (<<) im Befehl, in denen *Filename* angezeigt werden soll. Die spitzen Klammern einer makroerweiterung nicht möglich.

## <a name="syntax"></a>Syntax

```
<<[filename]
```

## <a name="remarks"></a>Hinweise

Wenn der Befehl ausgeführt wird, werden die spitzen Klammern durch ersetzt *Filename*(falls angegeben) bzw. durch einen eindeutigen Namen von NMAKE generiert. Wenn angegeben, *Filename* müssen die spitzen Klammern ohne ein Leerzeichen oder Tabstopp entsprechen. Ein Pfad ist zulässig. Keine Erweiterung ist erforderlich oder davon ausgegangen wird. Wenn *Filename* angegeben ist, wird die Datei wird erstellt, in der aktuellen oder das angegebene Verzeichnis überschreiben alle vorhandenen Datei mit diesem Namen; andernfalls wird es in der TMP-Verzeichnis erstellt (oder im aktuellen Verzeichnis, wenn die TMP-Umgebungsvariable ist nicht definiert). Bei Verwendung einer früheren *Filename* wird wiederverwendet, NMAKE ersetzt die vorherige Datei.

## <a name="see-also"></a>Siehe auch

[Inlinedateien in einem Makefile](../build/inline-files-in-a-makefile.md)