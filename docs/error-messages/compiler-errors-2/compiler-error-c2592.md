---
title: Compilerfehler C2592 | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C2592
dev_langs:
- C++
helpviewer_keywords:
- C2592
ms.assetid: 833a4d7b-66ef-4d4c-ae83-a533c2b0eb07
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 3528354797987b47379d0ec56e103223ac87892f
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c2592"></a>Compilerfehler C2592
„Klasse“: „base_class_2“ wird von „base_class_1“ geerbt und kann nicht erneut angegeben werden.  
  
 Sie können nur Basisklassen angeben, die nicht von anderen Basisklassen erben. In diesem Fall ist nur `base_class_1` in der Spezifikation von `class` erforderlich, da `base_class_1` bereits `base_class_2` erbt.