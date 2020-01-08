---
title: XMMWORD
ms.date: 12/17/2019
f1_keywords:
- XMMWORD
helpviewer_keywords:
- XMMWORD directive
ms.assetid: 18026d32-5cab-403e-ad7e-382fb41aa9b8
ms.openlocfilehash: 1116729883bf9b1b9342b30332bab5de6ba59015
ms.sourcegitcommit: 0781c69b22797c41630601a176b9ea541be4f2a3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/20/2019
ms.locfileid: "75319111"
---
# <a name="xmmword"></a>XMMWORD

Wird für 128-Bit-Multimedia-Operanden mit MMX-und SSE (XMM)-Anweisungen verwendet.

## <a name="syntax"></a>Syntax

> **XMMWORD**

## <a name="remarks"></a>Hinweise

**XMMWORD** soll denselben Typ wie [__m128](../../cpp/m128.md)darstellen.

## <a name="example"></a>Beispiel

```asm
    movdqa   xmm0, xmmword ptr [ebx]
```

## <a name="see-also"></a>Siehe auch

[MASM-BNF-Grammatik](masm-bnf-grammar.md)
