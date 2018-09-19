---
title: 'Platform:: recreateexception-Methode | Microsoft-Dokumentation'
ms.custom: ''
ms.date: 12/30/2016
ms.technology: cpp-windows
ms.topic: reference
f1_keywords:
- VCCORLIB/Platform::Exception
dev_langs:
- C++
helpviewer_keywords:
- Platform::Exception Class
ms.assetid: fa73d1ab-86e4-4d26-a7d9-81938c1c7e77
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 28434f6c8c35f2cd4cfc15953f761d28037626e6
ms.sourcegitcommit: 761c5f7c506915f5a62ef3847714f43e9b815352
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/07/2018
ms.locfileid: "44109718"
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
