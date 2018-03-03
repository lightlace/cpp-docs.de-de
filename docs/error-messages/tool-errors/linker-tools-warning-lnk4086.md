---
title: Linkertoolwarnung Lnk4086 | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- LNK4086
dev_langs:
- C++
helpviewer_keywords:
- LNK4086
ms.assetid: ea1eecbb-ba2c-41bb-9a4f-fa0808a4b92d
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: fcd701401c798d7126be4f4239ee533b14d90652
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="linker-tools-warning-lnk4086"></a>Linkertoolwarnung LNK4086
Einstiegspunkt 'Funktion' ist nicht __stdcall mit 'Anzahl' Bytes an Argumenten; Abbild kann möglicherweise nicht ausgeführt.  
  
 Der Einstiegspunkt für eine DLL muss `__stdcall`. Kompilieren Sie entweder die Funktion mit dem [/GZ](../../build/reference/gd-gr-gv-gz-calling-convention.md) aus oder geben Sie `__stdcall` oder WINAPI beim Definieren der Funktion.