---
title: Compilerwarnung (Stufe 1) C4049 | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4049
dev_langs:
- C++
helpviewer_keywords:
- C4049
ms.assetid: d11c1870-bcfc-4d71-8945-b87ec6ec3514
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 68a89d02129e5e8fbedb0649fff0cfe3813304c5
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/18/2018
ms.locfileid: "46053517"
---
# <a name="compiler-warning-level-1-c4049"></a>Compilerwarnung (Stufe 1) C4049

Compilerlimit: Ausgabe der Zeilennummer beenden

Die Datei enthält mehr als 16.777.215 (2<sup>24</sup>-1) Quellzeilen. Der Compiler wird die Nummerierung mit 16.777.215 beendet.

Für Code nach der Zeile 16.777.215:

- Das Image enthält keine Debuginformationen, damit die Zeilennummern.

- Eine Diagnose erfolgen, können mit falschen Zeilennummern angezeigt werden.

- ASM-Angebote (/ FAs) möglicherweise falsche Zeilennummern.