---
title: "-HIGHENTROPYVA (Unterstützung für 64-Bit-ASLR) | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
ms.assetid: fe35f9f7-d28e-4694-9aeb-a79db06168e0
caps.latest.revision: "6"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 059f6169cafc48fc67587ae2f5827966269e6ac7
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="highentropyva-support-64-bit-aslr"></a>/HIGHENTROPYVA (Unterstützung für 64-Bit ASLR)
Gibt an, dass das ausführbare Image 64-Bit-ASLR mit hoher Entropie unterstützt.  
  
## <a name="syntax"></a>Syntax  
  
```  
/HIGHENTROPYVA[:NO]  
```  
  
## <a name="remarks"></a>Hinweise  
 Standardmäßig ist „/HIGHENTROPYVA“ für ausführbare 64-Bit-Images aktiviert. Auf ausführbare 32-Bit-Images ist die Option nicht anwendbar. Um diese Option zu aktivieren, muss auch "/DYNAMICBASE" aktiviert sein.  
  
 Mit "/HIGHENTROPYVA" wird der Header einer DLL- oder EXE-Datei geändert, um anzugeben, ob ASLR mit 64-Bit-Adressen unterstützt wird. Wenn diese Option auf einer ausführbaren Datei und allen Modulen festgelegt wird, von denen sie abhängt, kann ein 64-Bit-ASLR unterstützendes Betriebssystem die Segmente des ausführbaren Images zur Ladezeit umbasieren, indem zufällige Adressen in einem virtuellen 64-Bit-Adressbereich verwendet werden. Aufgrund dieses großen Adressbereichs ist es für einen Angreifer schwieriger, den Ort eines bestimmten Speicherbereichs zu schätzen.  
  
### <a name="to-set-this-linker-option-in-visual-studio"></a>So legen Sie diese Linkeroption in Visual Studio fest  
  
1.  Öffnen Sie das Dialogfeld **Eigenschaftenseiten** des Projekts. Weitere Informationen finden Sie unter [arbeiten mit Projekteigenschaften](../../ide/working-with-project-properties.md).  
  
2.  Erweitern Sie die **Konfigurationseigenschaften** Knoten.  
  
3.  Erweitern Sie die **Linker** Knoten.  
  
4.  Wählen Sie die **Befehlszeile** Eigenschaftenseite.  
  
5.  In **Zusatzoptionen**, geben Sie `/HIGHENTROPYVA` oder `/HIGHENTROPYVA:NO`.  
  
## <a name="see-also"></a>Siehe auch  
 [Festlegen von Linkeroptionen](../../build/reference/setting-linker-options.md)   
 [Linkeroptionen](../../build/reference/linker-options.md)