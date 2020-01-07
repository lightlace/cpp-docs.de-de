---
title: tempnam
ms.date: 12/16/2019
api_name:
- tempnam
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
- tempnam
helpviewer_keywords:
- tempnam function
ms.assetid: 42446733-f131-470f-b4d0-96918becab11
ms.openlocfilehash: d4c7945b68a0cd8dd99fcf15e7484aad877c401d
ms.sourcegitcommit: a5fa9c6f4f0c239ac23be7de116066a978511de7
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/20/2019
ms.locfileid: "75300325"
---
# <a name="tempnam"></a>tempnam

Der von Microsoft implementierte Name der POSIX-Funktion `tempnam` ist ein als veraltet markierte Alias für die [_tempnam](tempnam-wtempnam-tmpnam-wtmpnam.md) -Funktion. Standardmäßig wird eine [Compilerwarnung (Ebene 3) C4996](../../error-messages/compiler-warnings/compiler-warning-level-3-c4996.md)generiert. Der Name ist veraltet, da er nicht den Standard mäßigen C-Regeln für Implementierungs spezifische Namen folgt. Die-Funktion wird jedoch weiterhin unterstützt.

Es wird empfohlen, stattdessen [_tempnam](tempnam-wtempnam-tmpnam-wtmpnam.md) zu verwenden. Oder Sie können diesen Funktionsnamen weiterhin verwenden und die Warnung deaktivieren. Weitere Informationen finden Sie unter [Deaktivieren der Namen der Warnungs](../../error-messages/compiler-warnings/compiler-warning-level-3-c4996.md#turn-off-the-warning) -und [POSIX-Funktionen](../../error-messages/compiler-warnings/compiler-warning-level-3-c4996.md#posix-function-names).
