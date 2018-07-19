---
title: Linkertoolwarnung Lnk4014 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- LNK4014
dev_langs:
- C++
helpviewer_keywords:
- LNK4014
ms.assetid: 394903e9-3ded-4ea4-b7c0-a3535d4b4da4
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 2fb86efbdc70342861a87a233ab687f7564cb48b
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33300058"
---
# <a name="linker-tools-warning-lnk4014"></a>Linkertoolwarnung LNK4014
Member-Objekt "Objectname" wurde nicht gefunden.  
  
 LIB wurde nicht gefunden. `objectname` in der Bibliothek.  
  
 Die **/REMOVE** und **/EXTRAHIEREN** Optionen muss der vollständige Name des Member-Objekt, das gelöscht oder in eine Datei kopiert werden. Der vollständige Name schließt den Pfad der ursprünglichen Objektdatei. Um den vollständigen Namen der Member-Objekte in einer Bibliothek anzuzeigen, verwenden Sie DUMPBIN [ARCHIVEMEMBERS](../../build/reference/archivemembers.md) oder LIB [/LIST](../../build/reference/managing-a-library.md).