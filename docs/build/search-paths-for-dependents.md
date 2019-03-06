---
title: Suchpfade für abhängige Dateien
ms.date: 11/04/2016
helpviewer_keywords:
- NMAKE program, dependents
- dependents, NMAKE
ms.assetid: bf998e47-da74-48b5-891d-d3d8ce57264b
ms.openlocfilehash: 9f2251a5fff9d708a783797d04606572e5ebce62
ms.sourcegitcommit: bff17488ac5538b8eaac57156a4d6f06b37d6b7f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/05/2019
ms.locfileid: "57426458"
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
