---
title: Schwerwiegender Fehler C1009 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C1009
dev_langs:
- C++
helpviewer_keywords:
- C1009
ms.assetid: dcc8383c-3362-4c47-9c26-25d2451ebd53
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 665d868aeacbaf5c62bf59a4400baa2b31569972
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="fatal-error-c1009"></a>Schwerwiegender Fehler C1009
Compilerlimit: zu tiefe Schachtelung von Makros  
  
 Der Compiler hat versucht, zu viele Makros gleichzeitig zu erweitern. Der Compiler hat einen Grenzwert von 256 Ebenen der Schachtelung von Makros. Teilen Sie geschachtelte Makros in einfachere Makros.