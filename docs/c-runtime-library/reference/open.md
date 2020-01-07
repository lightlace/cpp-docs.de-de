---
title: open
ms.date: 12/16/2019
api_name:
- open
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
- open
helpviewer_keywords:
- open function
ms.assetid: e3139118-4da2-434b-a551-fcf3fccf49b5
ms.openlocfilehash: 648f55511983264f127976b83a73dd5623717c14
ms.sourcegitcommit: a5fa9c6f4f0c239ac23be7de116066a978511de7
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/20/2019
ms.locfileid: "75301261"
---
# <a name="open"></a>open

Der von Microsoft implementierte Name der POSIX-Funktion `open` ist ein als veraltet markierte Alias für die [_open](open-wopen.md) -Funktion. Standardmäßig wird eine [Compilerwarnung (Ebene 3) C4996](../../error-messages/compiler-warnings/compiler-warning-level-3-c4996.md)generiert. Der Name ist veraltet, da er nicht den Standard mäßigen C-Regeln für Implementierungs spezifische Namen folgt. Die-Funktion wird jedoch weiterhin unterstützt.

Es wird empfohlen, stattdessen [_open](open-wopen.md) zu verwenden. Oder Sie können diesen Funktionsnamen weiterhin verwenden und die Warnung deaktivieren. Weitere Informationen finden Sie unter [Deaktivieren der Namen der Warnungs](../../error-messages/compiler-warnings/compiler-warning-level-3-c4996.md#turn-off-the-warning) -und [POSIX-Funktionen](../../error-messages/compiler-warnings/compiler-warning-level-3-c4996.md#posix-function-names).
