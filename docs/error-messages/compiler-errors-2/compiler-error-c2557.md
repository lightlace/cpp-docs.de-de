---
title: Compilerfehler C2557 | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: C2557
dev_langs: C++
helpviewer_keywords: C2557
ms.assetid: 48a33d82-aa16-4658-b346-2311fcb39864
caps.latest.revision: "6"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 1c52e0230504e9da79033def009aa8513c7e663c
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-error-c2557"></a>Compilerfehler C2557
"Bezeichner": Private und geschützte Member können nicht ohne Konstruktor initialisiert werden.  
  
 Nur Member und Freunde können einem privaten oder geschützten Member einen Wert zuweisen. Nicht öffentliche Member sollten im Klassenkonstruktor initialisiert werden.