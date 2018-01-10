---
title: LIB-Eingabedateien | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: Lib
dev_langs: C++
helpviewer_keywords: input files, LIB
ms.assetid: e1236f0d-cd90-446b-b900-f311f456085c
caps.latest.revision: "7"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 5fea7a8700eb2f5a5deee7afd05af8b0de0e4e71
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
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