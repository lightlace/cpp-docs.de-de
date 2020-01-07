---
title: strupr, wcsupr
ms.date: 12/16/2019
api_name:
- strupr
- wcsupr
api_location:
- msvcrt.dll
- msvcr80.dll
- msvcr90.dll
- msvcr100.dll
- msvcr100_clr0400.dll
- msvcr110.dll
- msvcr110_clr0400.dll
- msvcr120.dll
- msvcr120_clr0400.dll
- ucrtbase.dll
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- strupr
- wcsupr
helpviewer_keywords:
- strupr function
- wcsupr function
ms.assetid: 17dfe1cd-3b09-4702-9f89-2207f44953e6
ms.openlocfilehash: ce51eb4f7eeb80766e19cfdb4a39a3a7dd50d85a
ms.sourcegitcommit: a5fa9c6f4f0c239ac23be7de116066a978511de7
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/20/2019
ms.locfileid: "75300455"
---
# <a name="strupr-wcsupr"></a>strupr, wcsupr

Die Microsoft-spezifischen Funktionsnamen `strupr` und `wcsupr` sind als veraltet markierte Aliase für die Funktionen [_strupr und _wcsupr](strupr-strupr-l-mbsupr-mbsupr-l-wcsupr-l-wcsupr.md) . Standardmäßig generieren Sie eine [Compilerwarnung (Stufe 3) C4996](../../error-messages/compiler-warnings/compiler-warning-level-3-c4996.md). Die Namen sind veraltet, da Sie nicht den Standard mäßigen C-Regeln für Implementierungs spezifische Namen folgen. Die Funktionen werden jedoch weiterhin unterstützt.

Es wird empfohlen, stattdessen [_strupr und _wcsupr](strupr-strupr-l-mbsupr-mbsupr-l-wcsupr-l-wcsupr.md) bzw. die Funktionen für die Sicherheit mit erweiterter [_strupr_s und _wcsupr_s zu](strupr-s-strupr-s-l-mbsupr-s-mbsupr-s-l-wcsupr-s-wcsupr-s-l.md) verwenden. Oder Sie können diese Funktionsnamen weiterhin verwenden und die Warnung deaktivieren. Weitere Informationen finden Sie unter [Deaktivieren der Namen der Warnungs](../../error-messages/compiler-warnings/compiler-warning-level-3-c4996.md#turn-off-the-warning) -und [POSIX-Funktionen](../../error-messages/compiler-warnings/compiler-warning-level-3-c4996.md#posix-function-names).
