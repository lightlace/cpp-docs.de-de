---
title: Bildformat | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: conceptual
dev_langs:
- C++
ms.assetid: 3ca3654b-42fe-4253-9f2e-723644041aa0
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 356480333a62d998213726016f3940b318c218a0
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
---
# <a name="image-format"></a>Bildformat
Das ausführbare Image-Format ist PE32 +. Ausführbare Images (DLLs und EXEs) sind auf eine Maximalgröße von 2 GB beschränkt, die relativen Adressierung mit einer 32-Bit-Verschiebung verwendet werden kann um statische Image-Daten zu behandeln. Diese Daten enthalten den Import Local Address Table, Zeichenfolgenkonstanten, statischen globalen Daten und usw. an.  
  
## <a name="see-also"></a>Siehe auch  
 [x64-Softwarekonventionen](../build/x64-software-conventions.md)