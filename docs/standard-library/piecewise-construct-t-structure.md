---
title: Piecewise_contruct_t-Struktur
ms.date: 11/04/2016
f1_keywords:
- utility/std::piecewise_contruct_t
helpviewer_keywords:
- piecewise_contruct_t class
- piecewise_contruct_t structure
ms.openlocfilehash: 6a9a6af97ca5c7751d64cd1fa70c9d9eba87da7c
ms.sourcegitcommit: 3590dc146525807500c0477d6c9c17a4a8a2d658
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/16/2019
ms.locfileid: "68268362"
---
# <a name="piecewisecontructt-structure"></a>Piecewise_contruct_t-Struktur

Die Struktur `piecewise_construct_t` ist eine leere Struktur-Typ verwendet, um separate Konstruktor und beim Überladen von Funktionen zu. Insbesondere `pair` verfügt über einen Konstruktor mit `piecewise_construct_t` als das erste Argument, gefolgt von zwei `tuple` Argumente.

## <a name="syntax"></a>Syntax

```cpp
struct piecewise_construct_t { explicit piecewise_construct_t() = default; };

inline constexpr piecewise_construct_t piecewise_construct{};
```
