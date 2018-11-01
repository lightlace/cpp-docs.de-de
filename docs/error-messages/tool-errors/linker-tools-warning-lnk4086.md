---
title: Linkertoolwarnung LNK4086
ms.date: 11/04/2016
f1_keywords:
- LNK4086
helpviewer_keywords:
- LNK4086
ms.assetid: ea1eecbb-ba2c-41bb-9a4f-fa0808a4b92d
ms.openlocfilehash: c6a5a0714e070e6cf3aee8efcdfbdfa07fa9ee69
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50427858"
---
# <a name="linker-tools-warning-lnk4086"></a>Linkertoolwarnung LNK4086

Einstiegspunkt 'Funktion' ist nicht __stdcall mit 'Number' Bytes an Argumenten; Image kann möglicherweise nicht ausgeführt.

Der Einstiegspunkt für eine DLL-Datei muss `__stdcall`. Kompilieren Sie entweder die Funktion mit dem [/GZ](../../build/reference/gd-gr-gv-gz-calling-convention.md) option aus, oder geben Sie `__stdcall` oder WINAPI beim Definieren der Funktion.