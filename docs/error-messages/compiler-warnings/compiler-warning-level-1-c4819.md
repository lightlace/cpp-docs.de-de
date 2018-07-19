---
title: Compilerwarnung (Stufe 1) C4819 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4819
dev_langs:
- C++
helpviewer_keywords:
- C4819
ms.assetid: c0316e85-249c-414d-9df0-622d077c6bc2
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 718e0783c3f7afcc9af958f7940f437ac4c944b7
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33283379"
---
# <a name="compiler-warning-level-1-c4819"></a>Compilerwarnung (Stufe 1) C4819
Die Datei enthält ein Zeichen, das in der aktuellen Codepage (Nummer) nicht dargestellt werden kann. Speichern Sie die Datei im Unicode-Format, um Datenverluste zu vermeiden.  
  
 C4819 tritt auf, wenn eine ANSI-Quelldatei auf einem System mit einer Codepage kompiliert wird, die nicht alle Zeichen in der Datei darstellen kann.  
  
 Um C4819 zu beheben, speichern Sie die Datei im Unicode-Format. Wählen Sie in Visual Studio **Datei**, **Erweiterte Speicheroptionen**. In der **Erweiterte Speicheroptionen** Dialogfeld wählen eine Codierung, die alle Zeichen in der Datei darstellen kann – z. B. UTF-8 – und wählen Sie dann **OK**.