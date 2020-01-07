---
title: getpid
ms.date: 12/16/2019
api_name:
- getpid
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
- getpid
helpviewer_keywords:
- getpid function
ms.assetid: 4eaabab4-362b-429f-854e-ae4941919824
ms.openlocfilehash: 22ae4d0f5d9da6157d204aee89c3f60544580b97
ms.sourcegitcommit: a5fa9c6f4f0c239ac23be7de116066a978511de7
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/20/2019
ms.locfileid: "75300975"
---
# <a name="getpid"></a>getpid

Der von Microsoft implementierte Name der POSIX-Funktion `getpid` ist ein als veraltet markierte Alias für die [_getpid](getpid.md) -Funktion. Standardmäßig wird eine [Compilerwarnung (Ebene 3) C4996](../../error-messages/compiler-warnings/compiler-warning-level-3-c4996.md)generiert. Der Name ist veraltet, da er nicht den Standard mäßigen C-Regeln für Implementierungs spezifische Namen folgt. Die-Funktion wird jedoch weiterhin unterstützt.

Es wird empfohlen, stattdessen [_getpid](getpid.md) zu verwenden. Oder Sie können diesen Funktionsnamen weiterhin verwenden und die Warnung deaktivieren. Weitere Informationen finden Sie unter [Deaktivieren der Namen der Warnungs](../../error-messages/compiler-warnings/compiler-warning-level-3-c4996.md#turn-off-the-warning) -und [POSIX-Funktionen](../../error-messages/compiler-warnings/compiler-warning-level-3-c4996.md#posix-function-names).

> [!IMPORTANT]
> Diese API kann nicht in Anwendungen verwendet werden, die in Windows-Runtime ausgeführt werden. Weitere Informationen finden Sie im Artikel [CRT functions not supported in Universal Windows Platform apps (In Apps für die universelle Windows-Plattform nicht unterstützte CRT-Funktionen)](../../cppcx/crt-functions-not-supported-in-universal-windows-platform-apps.md).
