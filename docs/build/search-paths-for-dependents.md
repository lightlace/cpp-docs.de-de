---
title: Suchpfade für abhängige Dateien | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- NMAKE program, dependents
- dependents, NMAKE
ms.assetid: bf998e47-da74-48b5-891d-d3d8ce57264b
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: d1fd407f99abb98fb949b6d5bcc45b10c6ff9121
ms.sourcegitcommit: 92f2fff4ce77387b57a4546de1bd4bd464fb51b6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/17/2018
ms.locfileid: "45706298"
---
# <a name="search-paths-for-dependents"></a>Suchpfade für abhängige Dateien

Jedes abhängige hat einen optionalen Suchpfad, die wie folgt angegeben:

## <a name="syntax"></a>Syntax

```
{directory[;directory...]}dependent
```

## <a name="remarks"></a>Hinweise

NMAKE: Sucht ein abhängiges Element zunächst im aktuellen Verzeichnis, und klicken Sie dann in Verzeichnissen, in der angegebenen Reihenfolge aus. Ein Makro kann teilweise oder vollständig einen Suchpfad angeben. Schließen Sie Verzeichnisnamen in geschweifte Klammern ({}); Trennen Sie mehrere Verzeichnisse durch ein Semikolon (;). Es sind keine Leerzeichen oder Tabstopps zulässig.

## <a name="see-also"></a>Siehe auch

[Abhängige Dateien](../build/dependents.md)