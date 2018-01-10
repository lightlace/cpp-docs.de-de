---
title: Verwenden mehrerer Resultsets aus einer gespeicherten Prozedur | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- stored procedures, returning result sets
- multiple result sets
ms.assetid: c450c12c-a76c-4ae4-9675-071a41eeac05
caps.latest.revision: "7"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: ec887f01e377ffa6295086bbeeb56dcd884d6276
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="using-multiple-result-sets-from-one-stored-procedure"></a>Verwenden mehrerer Resultsets aus einer gespeicherten Prozedur
Die meisten gespeicherte Prozeduren zurückgeben mehrere Resultsets. Eine solche gespeicherte Prozedur enthält in der Regel eine oder mehrere select-Anweisungen. Der Consumer muss dies die Resultsets verarbeiten sollte.  
  
### <a name="to-handle-multiple-result-sets"></a>Um mehrere Resultsets verarbeiten legt sie fest  
  
1.  Erstellen einer `CCommand` -Klasse mit `CMultipleResults` als Vorlagenargument und mit dem Accessor auf Ihrer Wahl. Dies ist normalerweise einen dynamischen oder manuellen Accessor. Wenn Sie einen anderen Typ des Accessors verwenden, können Sie nicht die Ausgabespalten für jedes Rowset zu ermitteln sein.  
  
2.  Führen Sie die gespeicherte Prozedur wie gewohnt und binden Sie die Spalten (siehe [Gewusst wie: Abrufen von Daten?](../../data/oledb/fetching-data.md)).  
  
3.  Verwenden Sie die Daten an.  
  
4.  Rufen Sie `GetNextResult` auf die `CCommand` Klasse. Wenn eine andere Ergebnisrowset verfügbar ist, wird `GetNextResult` gibt S_OK zurück, und Sie sollten Ihre Spalten erneut binden, wenn Sie einen manuellen Accessor verwenden. Wenn `GetNextResult` einen Fehler zurückgibt, es sind keine weiteren Resultsets nach zur Verfügung.  
  
## <a name="see-also"></a>Siehe auch  
 [Verwenden von gespeicherten Prozeduren](../../data/oledb/using-stored-procedures.md)