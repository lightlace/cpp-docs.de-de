---
title: Mehrere Inlinedateien
ms.date: 11/04/2016
helpviewer_keywords:
- inline files, multiple NMAKE
- multiple inline files
- NMAKE program, inline files
ms.assetid: 6d381dcf-0ed8-45d1-8df3-b4598d860b99
ms.openlocfilehash: 5b41d448c89ac30d891c41d1ad1e314cbf9724a8
ms.sourcegitcommit: bff17488ac5538b8eaac57156a4d6f06b37d6b7f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/05/2019
ms.locfileid: "57425613"
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
