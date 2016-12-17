---
title: "Linkertoolfehler LNK2005"
ms.custom: na
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "error-reference"
f1_keywords: 
  - "LNK2005"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "LNK2005"
ms.assetid: d9587adc-68be-425c-8a30-15dbc86717a4
caps.latest.revision: 14
caps.handback.revision: "14"
ms.author: "corob"
manager: "ghogen"
---
# Linkertoolfehler LNK2005
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Bereits im Objekt definiertes Symbol  
  
 Das gegebene `symbol`, angezeigt in seiner ergänzten Form, wurde mehrfach definiert.  
  
 Weitere Informationen finden Sie in den Knowledge Base\-Artikeln:  
  
-   "LNK2005\-Fehler bei falscher Verknüpfung von CRT\-Bibliothek und MFC\-Bibliotheken in Visual C\+\+" \(Q148652\)  
  
-   "Global überladener delete\-Operator verursacht LNK2005" \(Q140440\)  
  
-   "LNK2005\-Fehler bei neu und delete bei Definition von \_ATL\_MIN\_CRT" \(Q184235\).  
  
 Knowledge Base\-Artikel finden Sie auf der MSDN Library\-CD\-ROM oder unter [http:\/\/support.microsoft.com\/search](http://support.microsoft.com/search).  
  
 Diesem Fehler folgt der schwerwiegende Fehler [LNK1169](../../error-messages/tool-errors/linker-tools-error-lnk1169.md).  
  
### Dieser Fehler kann eine der folgenden Ursachen haben:  
  
1.  Mischen von statischen und dynamischen Bibliotheken bei gleichzeitiger Verwendung von [\/clr](../../build/reference/clr-common-language-runtime-compilation.md).  
  
2.  Das Symbol ist eine Paketfunktion \(erstellt durch Kompilierung mit [\/Gy](../../build/reference/gy-enable-function-level-linking.md)\) und wurde in mehr als eine Datei eingefügt, aber zwischen Kompilationen geändert.  Kompilieren Sie alle Dateien neu, die `symbol` enthalten.  
  
3.  Das Symbol wird in zwei Memberobjekten in verschiedenen Bibliotheken unterschiedlich definiert, und beide Memberobjekte wurden verwendet.  
  
4.  Ein Absolut wurde zweimal definiert, mit einem unterschiedlichen Wert in jeder Definition.  
  
5.  Eine Headerdatei hat eine Variable deklariert und definiert.  Folgende Lösungen sind möglich:  
  
    -   Deklarieren Sie die Variable in .h: `extern BOOL MyBool;`, und legen Sie dann eine Zuordnung darauf in einer .c\- oder .cpp\-Datei fest: `BOOL MyBool = FALSE;`.  
  
    -   Deklarieren Sie die Variable [static](../../misc/static-cpp.md).  
  
    -   Deklarieren Sie die Variable [selectany](../../cpp/selectany.md).  
  
6.  Wenn Sie uuid.lib in Kombination mit anderen .lib\-Dateien verwenden, die GUIDs definieren \(zum Beispiel oledb.lib und adsiid.lib\).  Beispiel:  
  
    ```  
    oledb.lib(oledb_i.obj) : error LNK2005: _IID_ITransactionObject  
    already defined in uuid.lib(go7.obj)  
    ```  
  
     Fügen Sie als Korrektur [\/FORCE:MULTIPLE](../../build/reference/force-force-file-output.md) zu den Linker\-Befehlszeilenoptionen hinzu, und stellen Sie sicher, dass uuid.lib die zuerst referenzierte Bibliothek ist.