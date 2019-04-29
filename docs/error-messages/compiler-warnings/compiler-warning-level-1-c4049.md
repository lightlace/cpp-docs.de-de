---
title: Compilerwarnung (Stufe 1) C4049
ms.date: 11/04/2016
f1_keywords:
- C4049
helpviewer_keywords:
- C4049
ms.assetid: d11c1870-bcfc-4d71-8945-b87ec6ec3514
ms.openlocfilehash: a4958bb446b5f7e80ef2eef92b52a0f86cf6a134
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62388761"
---
# <a name="compiler-warning-level-1-c4049"></a>Compilerwarnung (Stufe 1) C4049

Compilerlimit: Ausgabe der Zeilennummer beenden

Die Datei enthält mehr als 16.777.215 (2<sup>24</sup>-1) Quellzeilen. Der Compiler wird die Nummerierung mit 16.777.215 beendet.

Für Code nach der Zeile 16.777.215:

- Das Image enthält keine Debuginformationen, damit die Zeilennummern.

- Eine Diagnose erfolgen, können mit falschen Zeilennummern angezeigt werden.

- ASM-Angebote (/ FAs) möglicherweise falsche Zeilennummern.