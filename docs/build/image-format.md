---
title: Bildformat | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
ms.assetid: 3ca3654b-42fe-4253-9f2e-723644041aa0
caps.latest.revision: "8"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: c0761acfe02b7d86f9316d06913de15347e9d522
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="image-format"></a>Bildformat
Das ausführbare Image-Format ist PE32 +. Ausführbare Images (DLLs und EXEs) sind auf eine Maximalgröße von 2 GB beschränkt, die relativen Adressierung mit einer 32-Bit-Verschiebung verwendet werden kann um statische Image-Daten zu behandeln. Diese Daten enthalten den Import Local Address Table, Zeichenfolgenkonstanten, statischen globalen Daten und usw. an.  
  
## <a name="see-also"></a>Siehe auch  
 [x64-Softwarekonventionen](../build/x64-software-conventions.md)