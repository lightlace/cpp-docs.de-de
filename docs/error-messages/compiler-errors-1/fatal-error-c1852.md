---
title: Schwerwiegender Fehler C1852 | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C1852
dev_langs:
- C++
helpviewer_keywords:
- C1852
ms.assetid: fa011004-b8d6-46f1-ba80-4785e4ce137f
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 0adfa7eed25f1902300fa2378b8ffc19eb8dfafd
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/18/2018
ms.locfileid: "46023799"
---
# <a name="fatal-error-c1852"></a>Schwerwiegender Fehler C1852

'Dateiname' ist keine gültige vorkompilierte Headerdatei.

Die Datei ist kein vorkompilierter Header.

### <a name="to-fix-by-checking-the-following-possible-causes"></a>Dieser Fehler kann eine der folgenden Ursachen haben:

1. Es wurde eine ungültige Datei mit **/Yu** oder **#pragma hdrstop**angegeben.

1. Wenn Sie keine andere Angabe vornehmen, nimmt der Compiler die Dateierweiterung PCH an.