---
title: spawnlpe
ms.date: 12/16/2019
api_name:
- spawnlpe
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
- spawnlpe
helpviewer_keywords:
- spawnlpe function
ms.assetid: 379143a7-f3d0-41de-83cc-2b4321146390
ms.openlocfilehash: e0dd321c26e02989898016c1ea707f6b6de886ff
ms.sourcegitcommit: a5fa9c6f4f0c239ac23be7de116066a978511de7
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/20/2019
ms.locfileid: "75300728"
---
# <a name="spawnlpe"></a>spawnlpe

Der Microsoft-spezifische Funktionsname `spawnlpe` ist ein als veraltet markierte Alias für die [_spawnlpe](spawnlpe-wspawnlpe.md) -Funktion. Standardmäßig wird eine [Compilerwarnung (Ebene 3) C4996](../../error-messages/compiler-warnings/compiler-warning-level-3-c4996.md)generiert. Der Name ist veraltet, da er nicht den Standard mäßigen C-Regeln für Implementierungs spezifische Namen folgt. Die-Funktion wird jedoch weiterhin unterstützt.

Es wird empfohlen, stattdessen [_spawnlpe](spawnlpe-wspawnlpe.md) zu verwenden. Oder Sie können diesen Funktionsnamen weiterhin verwenden und die Warnung deaktivieren. Weitere Informationen finden Sie unter [Deaktivieren der Namen der Warnungs](../../error-messages/compiler-warnings/compiler-warning-level-3-c4996.md#turn-off-the-warning) -und [POSIX-Funktionen](../../error-messages/compiler-warnings/compiler-warning-level-3-c4996.md#posix-function-names).

> [!IMPORTANT]
> Diese API kann nicht in Anwendungen verwendet werden, die in Windows-Runtime ausgeführt werden. Weitere Informationen finden Sie im Artikel [CRT functions not supported in Universal Windows Platform apps (In Apps für die universelle Windows-Plattform nicht unterstützte CRT-Funktionen)](../../cppcx/crt-functions-not-supported-in-universal-windows-platform-apps.md).
