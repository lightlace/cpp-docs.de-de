---
title: Linkertoolfehler Lnk2005 | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- LNK2005
dev_langs:
- C++
helpviewer_keywords:
- LNK2005
ms.assetid: d9587adc-68be-425c-8a30-15dbc86717a4
caps.latest.revision: 14
author: corob-msft
ms.author: corob
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Machine Translation
ms.sourcegitcommit: 4ac033535632e94a365aa8dafd849f2ab28a3af7
ms.openlocfilehash: bf93f364b3dc7156a62eb1c474177eb7b85c7827
ms.lasthandoff: 02/24/2017

---
# <a name="linker-tools-error-lnk2005"></a>Linkertoolfehler LNK2005
Bereits im Objekt definiertes Symbol  
  
Das gegebene `symbol`, angezeigt in seiner ergänzten Form, wurde mehrfach definiert.  
  
Weitere Informationen finden Sie in den Knowledge Base-Artikeln:  
  
-   [LNK2005-Fehler bei der CRT-Bibliothek und MFC-Bibliotheken, in der falschen Reihenfolge in Visual C++ verknüpft sind](https://support.microsoft.com/kb/148652)  
  
-   [FIX: Global überladener Delete-Operator verursacht LNK2005](https://support.microsoft.com/kb/140440)  
  
-   [Sie erhalten LNK2005-Fehler beim Kompilieren eines ATL-ausführbare Dateien (.exe)-Projekts in Visual C++](https://support.microsoft.com/kb/184235).  
  
Diesem Fehler folgt der schwerwiegende Fehler [LNK1169](../../error-messages/tool-errors/linker-tools-error-lnk1169.md).  
  
### <a name="to-fix-by-checking-the-following-possible-causes"></a>Dieser Fehler kann eine der folgenden Ursachen haben:  
  
1.  Mischen von statischen und dynamischen Bibliotheken bei gleichzeitiger Verwendung [/CLR](../../build/reference/clr-common-language-runtime-compilation.md).  
  
2.  Das Symbol ist eine Paketfunktion (erstellt durch Kompilierung mit [/Gy](../../build/reference/gy-enable-function-level-linking.md)) und in mehr als eine Datei enthalten war, aber zwischen Kompilationen geändert. Kompilieren Sie alle Dateien neu, die `symbol` enthalten.  
  
3.  Das Symbol wird in zwei Memberobjekten in verschiedenen Bibliotheken unterschiedlich definiert, und beide Memberobjekte wurden verwendet.  
  
4.  Ein Absolut wurde zweimal definiert, mit einem unterschiedlichen Wert in jeder Definition.  
  
5.  Eine Headerdatei hat eine Variable deklariert und definiert. Folgende Lösungen sind möglich:  
  
    -   Deklarieren Sie die Variable in .h: `extern BOOL MyBool;`, und legen Sie dann eine Zuordnung darauf in einer .c- oder .cpp-Datei fest: `BOOL MyBool = FALSE;`.  
  
    -   Deklarieren Sie die Variable [statische](../../cpp/storage-classes-cpp.md#static).  
  
    -   Deklarieren Sie die Variable [Selectany](../../cpp/selectany.md).  
  
6.  Wenn Sie uuid.lib in Kombination mit anderen .lib-Dateien verwenden, die GUIDs definieren (zum Beispiel oledb.lib und adsiid.lib). Zum Beispiel:  
  
    ```  
    oledb.lib(oledb_i.obj) : error LNK2005: _IID_ITransactionObject  
    already defined in uuid.lib(go7.obj)  
    ```  
  
     Um das Problem zu beheben, fügen [/Force: Multiple](../../build/reference/force-force-file-output.md) an den Linker-Befehlszeilenoptionen, und stellen Sie sicher, dass uuid.lib die zuerst referenzierte Bibliothek ist.
