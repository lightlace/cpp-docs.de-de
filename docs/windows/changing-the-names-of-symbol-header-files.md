---
title: Ändern der Namen von Symbolheaderdateien | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: conceptual
f1_keywords:
- vc.editors.symbol.changing.header
dev_langs:
- C++
helpviewer_keywords:
- resource files, multiple
- Resource Includes dialog box
- symbol header files, changing names
- symbol header files
- header files, changing names
- names [C++], symbol header files
- symbols, symbol header files
- Resource.h
ms.assetid: b948284a-7899-402e-ab12-9f2c8480ca9d
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 953ac59958748bd58fa7e9027c595bf7905e5f27
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/08/2018
---
# <a name="changing-the-names-of-symbol-header-files"></a>Ändern der Namen von Symbolheaderdateien
Normalerweise werden alle Symboldefinitionen in der Datei Resource.h gespeichert. Jedoch müssen Sie den Namen dieser Includedatei möglicherweise ändern, sodass Sie z. B. mit mehr als eine Ressourcendatei im selben Verzeichnis arbeiten können.  
  
### <a name="to-change-the-name-of-the-resource-symbol-header-file"></a>So ändern Sie den Namen den Symbolheaderdatei für die Ressource  
  
1.  In [Ressourcenansicht](../windows/resource-view-window.md)mit der rechten Maustaste auf die RC-Datei, und wählen Sie [Ressourcenincludes](../windows/resource-includes-dialog-box.md) aus dem Kontextmenü.  
  
    > [!NOTE]
    >  Wenn das Projekt noch keine RC-Datei enthält, informieren Sie sich unter [Erstellen einer neuen Ressourcenskriptdatei](../windows/how-to-create-a-resource-script-file.md).  
  
2.  In der **Symbolheaderdatei** geben den neuen Namen für die Includedatei.  
  
 Informationen zum Hinzufügen von Ressourcen zu verwalteten Projekten finden Sie unter [Ressourcen in Desktop-Apps](/dotnet/framework/resources/index) in die *.NET Framework-Entwicklerhandbuch.*  
  
 Anforderungen  
  
 Win32  
  
## <a name="see-also"></a>Siehe auch  
 [Anzeigen von Ressourcensymbolen](../windows/viewing-resource-symbols.md)   
 [Vordefinierte Symbol-IDs](../windows/predefined-symbol-ids.md)