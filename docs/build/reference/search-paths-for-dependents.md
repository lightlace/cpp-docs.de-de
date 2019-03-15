---
title: Suchpfade für abhängige Dateien
ms.date: 11/04/2016
helpviewer_keywords:
- NMAKE program, dependents
- dependents, NMAKE
ms.assetid: bf998e47-da74-48b5-891d-d3d8ce57264b
ms.openlocfilehash: bc2c430c43f408065234c9df50977003eafd3cb1
ms.sourcegitcommit: 8105b7003b89b73b4359644ff4281e1595352dda
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/14/2019
ms.locfileid: "57825461"
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

[Abhängige Dateien](dependents.md)
