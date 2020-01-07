---
title: dup, dup2
ms.date: 12/16/2019
api_name:
- dup2
- dup
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
- dup
- dup2
helpviewer_keywords:
- dup function
- dup2 function
ms.assetid: c7572170-47ff-4e0d-b9c3-10f0ab0ba40a
ms.openlocfilehash: ea6fe475b4a5e3cce5e9d05d89bd351361c2a4de
ms.sourcegitcommit: a5fa9c6f4f0c239ac23be7de116066a978511de7
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/20/2019
ms.locfileid: "75301209"
---
# <a name="dup-dup2"></a>dup, dup2

Die von Microsoft implementierten POSIX-Funktionsnamen `dup` und `dup2` sind veraltete Aliase für die Funktionen [_dup](dup-dup2.md) und [_dup2](dup-dup2.md) . Standardmäßig generieren Sie eine [Compilerwarnung (Stufe 3) C4996](../../error-messages/compiler-warnings/compiler-warning-level-3-c4996.md). Die Namen sind veraltet, da Sie nicht den Standard mäßigen C-Regeln für Implementierungs spezifische Namen folgen. Die Funktionen werden jedoch weiterhin unterstützt.

Es wird empfohlen, stattdessen [_dup](dup-dup2.md) und [_dup2](dup-dup2.md) zu verwenden. Oder Sie können diese Funktionsnamen weiterhin verwenden und die Warnung deaktivieren. Weitere Informationen finden Sie unter [Deaktivieren der Namen der Warnungs](../../error-messages/compiler-warnings/compiler-warning-level-3-c4996.md#turn-off-the-warning) -und [POSIX-Funktionen](../../error-messages/compiler-warnings/compiler-warning-level-3-c4996.md#posix-function-names).
