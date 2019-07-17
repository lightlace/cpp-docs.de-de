---
title: Bad_optional_access-Klasse
ms.date: 11/04/2016
f1_keywords:
- optional/std::bad_optional_access
ms.assetid: 89a3b805-ab60-4858-b772-5855130c11b1
ms.openlocfilehash: f898d1e30dd173339192bdb3b75581d12b62fca7
ms.sourcegitcommit: 3590dc146525807500c0477d6c9c17a4a8a2d658
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/16/2019
ms.locfileid: "68269142"
---
# <a name="badoptionalaccess-class"></a>Bad_optional_access-Klasse

Definiert den Typ der Objekte, die ausgelöst wird, wie Ausnahmen, um die Situation zu melden, es, in denen versucht wird Zugriff auf den Wert von, einem `optional` -Objekt, das keinen Wert enthält.

## <a name="syntax"></a>Syntax

```cpp
class bad_optional_access : public exception
{
    public: bad_optional_access();
};
```
