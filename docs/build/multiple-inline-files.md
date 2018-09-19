---
title: Mehrere Inlinedateien | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- inline files, multiple NMAKE
- multiple inline files
- NMAKE program, inline files
ms.assetid: 6d381dcf-0ed8-45d1-8df3-b4598d860b99
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 87d68034c4f0018d65020915d24d0b5c2ec5d61a
ms.sourcegitcommit: 92f2fff4ce77387b57a4546de1bd4bd464fb51b6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/17/2018
ms.locfileid: "45725594"
---
# <a name="multiple-inline-files"></a>Mehrere Inlinedateien

Ein Befehl kann mehr als eine Inlinedatei erstellen.

## <a name="syntax"></a>Syntax

```
command << <<
inlinetext
<<[KEEP | NOKEEP]
inlinetext
<<[KEEP | NOKEEP]
```

## <a name="remarks"></a>Hinweise

Geben Sie für jede Datei eine oder mehrere Textzeilen Inline gefolgt von einer schließenden-Zeile, die das Trennzeichen enthält. Beginnen Sie mit der zweiten Datei Text in der Zeile nach der begrenzenden Zeile für die erste Datei.

## <a name="see-also"></a>Siehe auch

[Inlinedateien in einem Makefile](../build/inline-files-in-a-makefile.md)