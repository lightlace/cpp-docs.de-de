---
title: Concurrency-Namespace-Konstanten (AMP)
ms.date: 11/04/2016
f1_keywords:
- amp/Concurrency::HLSL_MAX_NUM_BUFFERS
- amp/Concurrency::MODULENAME_MAX_LENGTH
ms.assetid: 13a8e8cd-2eec-4e60-a91d-5d271072747b
ms.openlocfilehash: e345fcf052fe3e293fbe1df14138873aa6977a18
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50551995"
---
# <a name="concurrency-namespace-constants-amp"></a>Concurrency-Namespace-Konstanten (AMP)

|||
|-|-|
|[HLSL_MAX_NUM_BUFFERS](#hlsl_max_num_buffers)|[MODULENAME_MAX_LENGTH](#modulename_max_length)|

##  <a name="hlsl_max_num_buffers"></a>  HLSL_MAX_NUM_BUFFERS-Konstante

Die maximale Anzahl der von DirectX zugelassenen Puffer.

```
static const UINT HLSL_MAX_NUM_BUFFERS = 64 + 128;
```

##  <a name="modulename_max_length"></a>  MODULENAME_MAX_LENGTH-Konstante

Speichert die maximale Länge des Modulnamens. Dieser Wert muss für den Compiler und die Laufzeit identisch sein.

```
static const UINT MODULENAME_MAX_LENGTH = 1024;
```

## <a name="see-also"></a>Siehe auch

[Concurrency-Namespace (C++ AMP)](concurrency-namespace-cpp-amp.md)
