---
title: sopen
ms.date: 12/16/2019
api_name:
- sopen
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
- sopen
helpviewer_keywords:
- sopen function
ms.assetid: 1ce0b707-0c9e-4942-8467-ce7f6cd68acc
ms.openlocfilehash: 83ec3ee87f16d37d651b2e7a37e0f7eaebe0f46d
ms.sourcegitcommit: a5fa9c6f4f0c239ac23be7de116066a978511de7
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/20/2019
ms.locfileid: "75300715"
---
# <a name="sopen"></a>sopen

Der Microsoft-spezifische Funktionsname `sopen` ist ein als veraltet markierte Alias für die [_sopen](sopen-wsopen.md) -Funktion. Standardmäßig wird eine [Compilerwarnung (Ebene 3) C4996](../../error-messages/compiler-warnings/compiler-warning-level-3-c4996.md)generiert. Der Name ist veraltet, da er nicht den Standard mäßigen C-Regeln für Implementierungs spezifische Namen folgt. Die-Funktion wird jedoch weiterhin unterstützt.

Es wird empfohlen, stattdessen [_sopen](sopen-wsopen.md) oder die [_sopen_s](sopen-s-wsopen-s.md) Funktion mit erweiterter Sicherheit zu verwenden. Oder Sie können diesen Funktionsnamen weiterhin verwenden und die Warnung deaktivieren. Weitere Informationen finden Sie unter [Deaktivieren der Namen der Warnungs](../../error-messages/compiler-warnings/compiler-warning-level-3-c4996.md#turn-off-the-warning) -und [POSIX-Funktionen](../../error-messages/compiler-warnings/compiler-warning-level-3-c4996.md#posix-function-names).
