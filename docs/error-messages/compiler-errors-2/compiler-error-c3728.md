---
title: Compilerfehler C3728 | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C3728
dev_langs:
- C++
helpviewer_keywords:
- C3728
ms.assetid: 6b510cb1-887f-4fcd-9a1f-3bb720417ed1
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: d20a0772a38dadc5956e1d174a23ecb0a8593647
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c3728"></a>Compilerfehler C3728
'Ereignis': Ereignis verfügt nicht über eine Raise-Methode  
  
 Metadaten erstellt mit einer anderen Sprache, z. B. c#, die kein Ereignis zulässt, das von außerhalb der Klasse ausgelöst werden, in dem es definiert wurde, enthalten war die [#using](../../preprocessor/hash-using-directive-cpp.md) Richtlinie und eine hat versucht, CLR-Programmierung mit Visual C++-Programm Lösen Sie das Ereignis.  
  
 Zum Auslösen eines Ereignisses in einem Programm, das in einer anderen Sprache wie c# entwickelt wurde, muss die Klasse, die das Ereignis enthält auch eine öffentliche Methode definieren, die das Ereignis auslöst.