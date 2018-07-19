---
title: Compilerfehler C2592 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2592
dev_langs:
- C++
helpviewer_keywords:
- C2592
ms.assetid: 833a4d7b-66ef-4d4c-ae83-a533c2b0eb07
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 5d999056d718d9c7aad93d08a99895caebbef539
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33229812"
---
# <a name="compiler-error-c2592"></a>Compilerfehler C2592
„Klasse“: „base_class_2“ wird von „base_class_1“ geerbt und kann nicht erneut angegeben werden.  
  
 Sie können nur Basisklassen angeben, die nicht von anderen Basisklassen erben. In diesem Fall ist nur `base_class_1` in der Spezifikation von `class` erforderlich, da `base_class_1` bereits `base_class_2` erbt.