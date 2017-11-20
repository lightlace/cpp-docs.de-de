---
title: Linkertoolwarnung Lnk4086 | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: LNK4086
dev_langs: C++
helpviewer_keywords: LNK4086
ms.assetid: ea1eecbb-ba2c-41bb-9a4f-fa0808a4b92d
caps.latest.revision: "8"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 85965c09bdbdff3ec271d2e1c5ef1913650009c3
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/24/2017
---
# <a name="linker-tools-warning-lnk4086"></a>Linkertoolwarnung LNK4086
Einstiegspunkt 'Funktion' ist nicht __stdcall mit 'Anzahl' Bytes an Argumenten; Abbild kann möglicherweise nicht ausgeführt.  
  
 Der Einstiegspunkt für eine DLL muss `__stdcall`. Kompilieren Sie entweder die Funktion mit dem [/GZ](../../build/reference/gd-gr-gv-gz-calling-convention.md) aus oder geben Sie `__stdcall` oder WINAPI beim Definieren der Funktion.