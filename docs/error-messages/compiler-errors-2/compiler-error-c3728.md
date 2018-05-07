---
title: Compilerfehler C3728 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3728
dev_langs:
- C++
helpviewer_keywords:
- C3728
ms.assetid: 6b510cb1-887f-4fcd-9a1f-3bb720417ed1
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: bae204db616db9e7d7e04cfd62d53374b0793aa9
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-error-c3728"></a>Compilerfehler C3728
'Ereignis': Ereignis verfügt nicht über eine Raise-Methode  
  
 Metadaten erstellt mit einer anderen Sprache, z. B. c#, die kein Ereignis zulässt, das von außerhalb der Klasse ausgelöst werden, in dem es definiert wurde, enthalten war die [#using](../../preprocessor/hash-using-directive-cpp.md) Richtlinie und eine hat versucht, CLR-Programmierung mit Visual C++-Programm Lösen Sie das Ereignis.  
  
 Zum Auslösen eines Ereignisses in einem Programm, das in einer anderen Sprache wie c# entwickelt wurde, muss die Klasse, die das Ereignis enthält auch eine öffentliche Methode definieren, die das Ereignis auslöst.