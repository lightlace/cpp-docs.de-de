---
title: Compilerwarnung (Stufe 1) C4678 | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: C4678
dev_langs: C++
helpviewer_keywords: C4678
ms.assetid: 0c588f34-595d-4e5c-9470-8723fca2cc06
caps.latest.revision: "10"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 52ebd41531cd5fdfd7aeb6ba6f52cf8981fa6120
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-warning-level-1-c4678"></a>Compilerwarnung (Stufe 1) C4678
Basisklasse "base_type" hat eine stärkere Zugriffsbeschränkung als "derived_type"  
  
Ein öffentlicher Typ wurde von einem privaten Typ abgeleitet. Wenn der öffentliche Typ in einer referenzierten Assembly instanziiert wird, sind die Member des privaten Basistyps nicht zugänglich.  
  
C4678 ist nur über die veraltete Compileroption erreichbar **/CLR: oldSyntax**. Es ist ein Fehler auf, wenn mit **"/ CLR"**, damit eine Basisklasse, die weniger zugegriffen werden kann, die abgeleitete Klasse.  
