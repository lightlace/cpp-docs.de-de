---
title: once_flag-Struktur
ms.date: 09/17/2018
f1_keywords:
- mutex/std::once_flag
ms.assetid: 71bfb88d-ca8c-4082-a6e1-ff52151e8629
ms.openlocfilehash: 004a5545e2eccab83b0846e2ae30b88c8431c99d
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62371437"
---
# <a name="onceflag-structure"></a>once_flag-Struktur

Stellt eine **Struktur** wird, mit der Vorlagenfunktion [Call_once](../standard-library/mutex-functions.md#call_once) um sicherzustellen, dass die Initialisierung ist Code auch bei mehreren Ausführungsthreads nur einmal aufgerufen.

## <a name="syntax"></a>Syntax

struct once_flag { constexpr once_flag() noexcept; };

## <a name="remarks"></a>Hinweise

Die `once_flag` **Struktur** verfügt über nur einen Standardkonstruktor.

Objekte vom Typ `once_flag` können erstellt, aber nicht kopiert werden.

## <a name="requirements"></a>Anforderungen

**Header:** \<mutex>

**Namespace:** std

## <a name="see-also"></a>Siehe auch

[Headerdateienreferenz](../standard-library/cpp-standard-library-header-files.md)<br/>
[\<mutex>](../standard-library/mutex.md)<br/>
