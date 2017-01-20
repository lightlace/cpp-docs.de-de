---
title: "Linkertoolwarnung LNK4086"
ms.custom: na
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "error-reference"
f1_keywords: 
  - "LNK4086"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "LNK4086"
ms.assetid: ea1eecbb-ba2c-41bb-9a4f-fa0808a4b92d
caps.latest.revision: 8
caps.handback.revision: "8"
ms.author: "corob"
manager: "ghogen"
---
# Linkertoolwarnung LNK4086
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Einstiegspunkt 'Funktion' ist nicht \_\_stdcall mit 'Anzahl' Bytes an Argumenten; Anwendung kann vielleicht nicht ausgeführt werden  
  
 Der Einstiegspunkt für eine DLL muss `__stdcall` sein.  Kompilieren Sie die Funktion entweder mit der [\/Gz](../../build/reference/gd-gr-gv-gz-calling-convention.md)\-Option neu, oder geben Sie `__stdcall` oder WINAPI beim Definieren der Funktion an.