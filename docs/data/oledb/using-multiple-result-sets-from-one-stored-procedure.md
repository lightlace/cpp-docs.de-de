---
title: Verwenden mehrerer Resultsets aus einer gespeicherten Prozedur
ms.date: 10/24/2018
helpviewer_keywords:
- stored procedures, returning result sets
- multiple result sets
ms.assetid: c450c12c-a76c-4ae4-9675-071a41eeac05
ms.openlocfilehash: 69e5c956d897e217501cbac9b9b93db868731221
ms.sourcegitcommit: c7f90df497e6261764893f9cc04b5d1f1bf0b64b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/05/2019
ms.locfileid: "59028424"
---
# <a name="using-multiple-result-sets-from-one-stored-procedure"></a>Verwenden mehrerer Resultsets aus einer gespeicherten Prozedur

Die meisten gespeicherte Prozeduren zurückgeben mehrere Resultsets. Eine solche gespeicherte Prozedur enthält in der Regel eine oder mehr select-Anweisungen. Der Consumer muss berücksichtigt diese Einbeziehung alle Resultsets verarbeiten.

## <a name="to-handle-multiple-result-sets"></a>Um mehrere Resultsets verarbeiten legt diese fest

1. Erstellen Sie eine `CCommand` Klasse mit `CMultipleResults` als Vorlagenargument und mit dem Accessor auf Ihrer Wahl, in der Regel einen dynamischen oder manuellen-Accessor. Wenn Sie einen anderen Typ des Accessors verwenden, Sie bestimmen die Ausgabespalten für jedes Rowset können möglicherweise nicht.

1. Führen Sie die gespeicherte Prozedur wie gewohnt und binden Sie die Spalten (finden Sie unter [Abrufen von Daten?](../../data/oledb/fetching-data.md)).

1. Verwenden Sie die Daten an.

1. Rufen Sie `GetNextResult` auf die `CCommand` Klasse. Wenn eine andere Ergebnisrowset verfügbar ist, `GetNextResult` gibt S_OK zurück, und Sie sollten Ihre Spalten erneut binden, wenn Sie einen manuellen Accessor verwenden. Wenn `GetNextResult` ein Fehler zurückgegeben, es sind keine weiteren Resultsets nach zur Verfügung.

## <a name="see-also"></a>Siehe auch

[Verwenden von gespeicherten Prozeduren](../../data/oledb/using-stored-procedures.md)