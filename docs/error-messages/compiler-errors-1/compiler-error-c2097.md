---
title: Compilerfehler C2097 | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2097
dev_langs:
- C++
helpviewer_keywords:
- C2097
ms.assetid: 7e5b2fd4-f61c-4b8a-b265-93e987a04bd3
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 2da955f5382a1ebacdb507a69ed02627b11462e5
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/18/2018
ms.locfileid: "46021862"
---
# <a name="compiler-error-c2097"></a>Compilerfehler C2097

Unzulässige Initialisierung

### <a name="to-fix-by-checking-the-following-possible-causes"></a>Dieser Fehler kann eine der folgenden Ursachen haben:

1. Die Initialisierung einer Variablen mit einem nicht konstanten Wert.

1. Die Initialisierung eine kurze Adresse mit einer long-Adresse.

1. Initialisierung von einer lokalen Struktur-, Union- oder Arrays mit einem nicht konstanten Ausdruck beim Kompilieren mit **/Za**.

1. Die Initialisierung mit einem Ausdruck mit einem Kommaoperator.

1. Die Initialisierung mit einem Ausdruck an, der weder konstant noch symbolische ist.