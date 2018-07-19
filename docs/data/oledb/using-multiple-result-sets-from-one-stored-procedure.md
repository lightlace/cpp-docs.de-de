---
title: Verwenden mehrerer Resultsets aus einer gespeicherten Prozedur | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- stored procedures, returning result sets
- multiple result sets
ms.assetid: c450c12c-a76c-4ae4-9675-071a41eeac05
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 6393901839e8450ebc45b11f1d4bd2250da2ca56
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33106309"
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