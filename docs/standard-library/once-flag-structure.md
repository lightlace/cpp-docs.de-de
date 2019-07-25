---
title: once_flag-Struktur
ms.date: 09/17/2018
f1_keywords:
- mutex/std::once_flag
ms.assetid: 71bfb88d-ca8c-4082-a6e1-ff52151e8629
ms.openlocfilehash: fb85bd48f9b1ac10ec2fefbc6738aae777f67bcf
ms.sourcegitcommit: 0dcab746c49f13946b0a7317fc9769130969e76d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/24/2019
ms.locfileid: "68455205"
---
# <a name="onceflag-structure"></a>once_flag-Struktur

Stellt eine **Struktur** dar, die mit der Vorlagen Funktion [call_once](../standard-library/mutex-functions.md#call_once) verwendet wird, um sicherzustellen, dass der Initialisierungs Code nur einmal aufgerufen wird, auch wenn mehrere Ausführungs Threads vorhanden sind.

## <a name="syntax"></a>Syntax

struct once_flag { constexpr once_flag() noexcept; };

## <a name="remarks"></a>Hinweise

Die `once_flag` **Struktur** verfügt über nur einen Standardkonstruktor.

Objekte vom Typ `once_flag` können erstellt, aber nicht kopiert werden.

## <a name="requirements"></a>Anforderungen

**Header:** \<mutex>

**Namespace:** std

## <a name="see-also"></a>Siehe auch

[Headerdateienreferenz](../standard-library/cpp-standard-library-header-files.md)\
[\<mutex>](../standard-library/mutex.md)
