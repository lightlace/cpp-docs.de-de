---
title: Linkertoolwarnung Lnk4086 | Microsoft Docs
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
ms.openlocfilehash: b7b3ad3a8ceebf97ccdcf7a1d8079886f54a3984
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="linker-tools-warning-lnk4086"></a>Linkertoolwarnung LNK4086
Einstiegspunkt 'Funktion' ist nicht __stdcall mit 'Anzahl' Bytes an Argumenten; Abbild kann möglicherweise nicht ausgeführt.  
  
 Der Einstiegspunkt für eine DLL muss `__stdcall`. Kompilieren Sie entweder die Funktion mit dem [/GZ](../../build/reference/gd-gr-gv-gz-calling-convention.md) aus oder geben Sie `__stdcall` oder WINAPI beim Definieren der Funktion.