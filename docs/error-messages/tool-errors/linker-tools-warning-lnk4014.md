---
title: Linkertoolwarnung Lnk4014 | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: LNK4014
dev_langs: C++
helpviewer_keywords: LNK4014
ms.assetid: 394903e9-3ded-4ea4-b7c0-a3535d4b4da4
caps.latest.revision: "8"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 8e0e0e87fb9c8e6006c62e07b7bb9b6435a22dd3
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="linker-tools-warning-lnk4014"></a>Linkertoolwarnung LNK4014
Member-Objekt "Objectname" wurde nicht gefunden.  
  
 LIB wurde nicht gefunden. `objectname` in der Bibliothek.  
  
 Die **/REMOVE** und **/EXTRAHIEREN** Optionen muss der vollständige Name des Member-Objekt, das gelöscht oder in eine Datei kopiert werden. Der vollständige Name schließt den Pfad der ursprünglichen Objektdatei. Um den vollständigen Namen der Member-Objekte in einer Bibliothek anzuzeigen, verwenden Sie DUMPBIN [ARCHIVEMEMBERS](../../build/reference/archivemembers.md) oder LIB [/LIST](../../build/reference/managing-a-library.md).