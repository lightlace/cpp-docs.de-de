---
title: Compilerfehler C2097
ms.date: 11/04/2016
f1_keywords:
- C2097
helpviewer_keywords:
- C2097
ms.assetid: 7e5b2fd4-f61c-4b8a-b265-93e987a04bd3
ms.openlocfilehash: 8b50221997dcf2fb60ee2b82ed630dd325a38145
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62377006"
---
# <a name="compiler-error-c2097"></a>Compilerfehler C2097

Unzulässige Initialisierung

### <a name="to-fix-by-checking-the-following-possible-causes"></a>Dieser Fehler kann eine der folgenden Ursachen haben:

1. Die Initialisierung einer Variablen mit einem nicht konstanten Wert.

1. Die Initialisierung eine kurze Adresse mit einer long-Adresse.

1. Initialisierung von einer lokalen Struktur-, Union- oder Arrays mit einem nicht konstanten Ausdruck beim Kompilieren mit **/Za**.

1. Die Initialisierung mit einem Ausdruck mit einem Kommaoperator.

1. Die Initialisierung mit einem Ausdruck an, der weder konstant noch symbolische ist.