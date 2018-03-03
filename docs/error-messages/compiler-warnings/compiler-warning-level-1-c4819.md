---
title: Compilerwarnung (Stufe 1) C4819 | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C4819
dev_langs:
- C++
helpviewer_keywords:
- C4819
ms.assetid: c0316e85-249c-414d-9df0-622d077c6bc2
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: b515a3f5e840bbc93f37420866023ee778b404ee
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-warning-level-1-c4819"></a>Compilerwarnung (Stufe 1) C4819
Die Datei enthält ein Zeichen, das in der aktuellen Codepage (Nummer) nicht dargestellt werden kann. Speichern Sie die Datei im Unicode-Format, um Datenverluste zu vermeiden.  
  
 C4819 tritt auf, wenn eine ANSI-Quelldatei auf einem System mit einer Codepage kompiliert wird, die nicht alle Zeichen in der Datei darstellen kann.  
  
 Um C4819 zu beheben, speichern Sie die Datei im Unicode-Format. Wählen Sie in Visual Studio **Datei**, **Erweiterte Speicheroptionen**. In der **Erweiterte Speicheroptionen** Dialogfeld wählen eine Codierung, die alle Zeichen in der Datei darstellen kann – z. B. UTF-8 – und wählen Sie dann **OK**.