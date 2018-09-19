---
title: Linkertoolwarnung LNK4086 | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- LNK4086
dev_langs:
- C++
helpviewer_keywords:
- LNK4086
ms.assetid: ea1eecbb-ba2c-41bb-9a4f-fa0808a4b92d
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 21a2ee7660f0ad78d04f7edb191929296c8d47a9
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/18/2018
ms.locfileid: "46079231"
---
# <a name="linker-tools-warning-lnk4086"></a>Linkertoolwarnung LNK4086

Einstiegspunkt 'Funktion' ist nicht __stdcall mit 'Number' Bytes an Argumenten; Image kann möglicherweise nicht ausgeführt.

Der Einstiegspunkt für eine DLL-Datei muss `__stdcall`. Kompilieren Sie entweder die Funktion mit dem [/GZ](../../build/reference/gd-gr-gv-gz-calling-convention.md) option aus, oder geben Sie `__stdcall` oder WINAPI beim Definieren der Funktion.