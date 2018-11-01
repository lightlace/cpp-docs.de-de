---
title: 'Platform:: recreateexception-Methode'
ms.date: 12/30/2016
ms.topic: reference
f1_keywords:
- VCCORLIB/Platform::Exception
helpviewer_keywords:
- Platform::Exception Class
ms.assetid: fa73d1ab-86e4-4d26-a7d9-81938c1c7e77
ms.openlocfilehash: 8173377a3d7a75bc85088037c229bac19f341649
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50568869"
---
# <a name="platformrecreateexception-method"></a>Platform::ReCreateException-Methode

Diese Methode ist nur für die interne Verwendung bestimmt und nicht für Benutzercode gedacht. Verwenden Sie stattdessen die Exception:: createexception-Methode.

## <a name="syntax"></a>Syntax

```cpp
static Exception^ ReCreateException(int hr)
```

### <a name="parameters"></a>Parameter

*HR*

### <a name="property-valuereturn-value"></a>Eigenschaftswert/Rückgabewert

Gibt eine neue Platform::Exception^ basierend auf dem angegebenen HRESULT zurück.
