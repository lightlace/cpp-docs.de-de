---
title: once_flag-Struktur
ms.date: 09/17/2018
f1_keywords:
- mutex/std::once_flag
ms.assetid: 71bfb88d-ca8c-4082-a6e1-ff52151e8629
ms.openlocfilehash: 004a5545e2eccab83b0846e2ae30b88c8431c99d
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50481970"
---
# <a name="onceflag-structure"></a>once_flag-Struktur

Stellt eine **Struktur** wird, mit der Vorlagenfunktion [Call_once](../standard-library/mutex-functions.md#call_once) um sicherzustellen, dass die Initialisierung ist Code auch bei mehreren Ausführungsthreads nur einmal aufgerufen.

## <a name="syntax"></a>Syntax

Struktur Once_flag {Constexpr once_flag() Noexcept;};

## <a name="remarks"></a>Hinweise

Die `once_flag` **Struktur** verfügt über nur einen Standardkonstruktor.

Objekte vom Typ `once_flag` können erstellt, aber nicht kopiert werden.

## <a name="requirements"></a>Anforderungen

**Header:** \<mutex>

**Namespace:** std

## <a name="see-also"></a>Siehe auch

[Headerdateienreferenz](../standard-library/cpp-standard-library-header-files.md)<br/>
[\<mutex>](../standard-library/mutex.md)<br/>
