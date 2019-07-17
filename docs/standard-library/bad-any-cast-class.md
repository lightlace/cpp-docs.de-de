---
title: Bad_any_cast-Klasse
ms.date: 04/04/2019
f1_keywords:
- any/std::bad_any_cast
- any/std::bad_any_cast::what
helpviewer_keywords:
- any/std::bad_any_cast
- any/std::bad_any_cast::what
ms.openlocfilehash: 5172281d1918a8b4ac33bcf412bf4be82b04ef56
ms.sourcegitcommit: 3590dc146525807500c0477d6c9c17a4a8a2d658
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/16/2019
ms.locfileid: "68268682"
---
# <a name="badanycast-class"></a>Bad_any_cast-Klasse

Objekte, die von einer fehlgeschlagenen ausgelöst `any_cast`.

## <a name="syntax"></a>Syntax

```cpp
class bad_any_cast
```

### <a name="member-functions"></a>Memberfunktionen

|||
|-|-|
|[Was](#what)|Gibt den Typ zurück.|

## <a name="what"></a> Was

Gibt den Typ zurück.

```cpp
const char* what() const noexcept override;
```
