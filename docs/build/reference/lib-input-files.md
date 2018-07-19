---
title: LIB-Eingabedateien | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- Lib
dev_langs:
- C++
helpviewer_keywords:
- input files, LIB
ms.assetid: e1236f0d-cd90-446b-b900-f311f456085c
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 140a0f1d9ef6fdb3ca5e6d6977804684c88af1fb
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
ms.locfileid: "32371966"
---
# <a name="lib-input-files"></a>LIB-Eingabedateien
Die Eingabedateien von LIB erwartet hängen von der Modus, in dem Programm verwendet wird, wie in der folgenden Tabelle gezeigt.  
  
|Modus|Eingabe|  
|----------|-----------|  
|Standard (erstellen oder Ändern einer Bibliothek)|COFF-Objektdateien (.obj), COFF-Bibliotheken (.lib), 32-Bit-Objekt Modell Format (OMF) Objektdateien (.obj)|  
|Extrahiert ein Element mit dem/Extract|COFF-Bibliothek (.lib)|  
|Erstellen einer Exportdatei und Importbibliothek mit/DEF|Moduldefinitionsdatei (.def), COFF-Objektdateien (.obj), COFF-Bibliotheken (.lib), 32-Bit-OMF-Objektdateien (obj)-Dateien|  
  
> [!NOTE]
>  OMF-Bibliotheken, die von der 16-Bit-Version von LIB erstellt, können nicht als Eingabe für die 32-Bit-Version von LIB verwendet werden.  
  
## <a name="see-also"></a>Siehe auch  
 [Übersicht über LIB](../../build/reference/overview-of-lib.md)