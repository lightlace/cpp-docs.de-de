---
title: Compilerfehler C2654 | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2654
dev_langs:
- C++
helpviewer_keywords:
- C2654
ms.assetid: ca7de1bd-576b-40bf-96fc-a91984827d20
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 1181cbab40739617343f8d2a2e5e26540f01e82f
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/18/2018
ms.locfileid: "46080843"
---
# <a name="compiler-error-c2654"></a>Compilerfehler C2654

'Bezeichner': Zugriff auf Element außerhalb einer Methode

Ein Member wird in einer Deklaration zugegriffen werden. Memberdaten können nur in Memberfunktionen zugegriffen werden.

Dieser Fehler kann verursacht werden, beim Versuch, die Variablen in einer Deklaration initialisiert werden. Verwenden Sie einen Konstruktor für diesen Zweck.