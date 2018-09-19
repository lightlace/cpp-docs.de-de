---
title: once_flag-Struktur | Microsoft-Dokumentation
ms.custom: ''
ms.date: 09/17/2018
ms.technology:
- cpp-standard-libraries
ms.topic: reference
f1_keywords:
- mutex/std::once_flag
dev_langs:
- C++
ms.assetid: 71bfb88d-ca8c-4082-a6e1-ff52151e8629
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 67cfbe06461598fbd04e124629399baa63fdd5d9
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/18/2018
ms.locfileid: "46104334"
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
