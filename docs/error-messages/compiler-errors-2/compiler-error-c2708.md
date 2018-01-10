---
title: Compilerfehler Fehler C2708 | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C2708
dev_langs: C++
helpviewer_keywords: C2708
ms.assetid: d52d3088-1141-42f4-829c-74755a7fcc3a
caps.latest.revision: "7"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 495fd9aeaad785edd8653e46ae666f60c337b12d
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c2708"></a>Compilerfehler Fehler C2708
'Bezeichner': Parameterlänge in Bytes unterscheidet sich vom vorherigen Aufruf oder Verweis  
  
 Ein [__stdcall](../../cpp/stdcall.md) Funktion muss einen Prototyp vorangestellt werden. Andernfalls, interpretiert der Compiler den ersten Aufruf der Funktion als Prototyp, und dieser Fehler tritt auf, wenn der Compiler einen Aufruf erkennt, der nicht übereinstimmen.  
  
 Fügen zum Beheben dieses Fehlers einen Funktionsprototyp.