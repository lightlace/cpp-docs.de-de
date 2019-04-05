---
title: Erfolgreiche Durchführung der OLE DB-Konformitätstests
ms.date: 11/04/2016
helpviewer_keywords:
- testing, OLE DB providers
- testing providers
- conformance testing
- conformance testing [OLE DB]
- OLE DB providers, testing
ms.assetid: d1a4f147-2edd-476c-b452-0e6a0ac09891
ms.openlocfilehash: 9f78b16bc30651560137a39286460a8e5ceccd40
ms.sourcegitcommit: c7f90df497e6261764893f9cc04b5d1f1bf0b64b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/05/2019
ms.locfileid: "59036996"
---
# <a name="passing-ole-db-conformance-tests"></a>Erfolgreiche Durchführung der OLE DB-Konformitätstests

Um Anbieter konsistenter zu machen, bietet der Data Access SDK einen Satz von OLE DB-Konformitätstests. Die Tests überprüfen Sie alle Aspekte des Anbieters ein, und geben Ihnen die Sicherheit, die der Anbieter erwartungsgemäß funktioniert. Der OLE DB-Konformitätstests finden Sie auf der Microsoft Data Access SDK. Dieser Abschnitt konzentriert sich auf Dinge, die Sie tun sollten, um die Konformitätstests besteht. Informationen zum Ausführen der OLE DB-Konformitätstests finden Sie im SDK.

## <a name="running-the-conformance-tests"></a>Ausführen der Konformitätstests

In Visual C++ 6.0 hinzugefügt, die OLE DB-Anbietervorlagen eine Reihe von hooking Funktionen, die Ihnen ermöglichen, Werte und Eigenschaften zu überprüfen. Die meisten dieser Funktionen wurden als Reaktion auf die Konformitätstests hinzugefügt.

> [!NOTE]
> Sie müssen mehrere Validierungsfunktionen für Ihren Anbieter, um die OLE DB-Konformitätstests besteht hinzufügen.

Der Anbieter erfordert zwei Überprüfungsroutinen. Die erste Routine, `CRowsetImpl::ValidateCommandID`, ist Teil der Rowsetklasse. Es wird während der Erstellung des Rowsets von die Anbietervorlagen aufgerufen werden. Das Beispiel verwendet diese Routine, um Consumern mitzuteilen, dass sie die Indizes nicht unterstützt. Der erste Aufruf `CRowsetImpl::ValidateCommandID` (Beachten Sie, die der Anbieter verwendet die `_RowsetBaseClass` Typedef, die hinzugefügt werden, in die schnittstellenzuordnung für `CCustomRowset` in [Anbieterunterstützung für Lesezeichen](../../data/oledb/provider-support-for-bookmarks.md), sodass Sie keine, lange Zeile in der Vorlage eingeben (Argumente). Als Nächstes zurückgegeben Sie DB_E_NOINDEX, wenn der Indexparameter nicht NULL ist, (was darauf hinweist, dass der Consumer einen Index verwenden möchte). Weitere Informationen zu den Befehls-IDs finden Sie in der OLE DB-Spezifikation, und suchen Sie nach `IOpenRowset::OpenRowset`.

Der folgende Code ist die `ValidateCommandID` Validierungsroutine:

```cpp
/////////////////////////////////////////////////////////////////////
// CustomRS.H
// Class: CCustomRowset

HRESULT ValidateCommandID(DBID* pTableID, DBID* pIndexID)
{
   HRESULT hr = _RowsetBaseClass::ValidateCommandID(pTableID, pIndexID);
   if (hr != S_OK)
      return hr;

   if (pIndexID != NULL)
      return DB_E_NOINDEX;    // Doesn't support indexes

   return S_OK;
}
```

Die Anbietervorlagen rufen die `OnPropertyChanged` -Methode auf, wenn jemand eine Eigenschaft in der DBPROPSET_ROWSET-Gruppe ändert. Sollten Sie die Eigenschaften für andere Gruppen zu behandeln, fügen Sie sie in das entsprechende Objekt (DBPROPSET_SESSION-Überprüfungen, also zu wechseln, der `CCustomSession` Klasse).

Der Code überprüft zuerst, um festzustellen, ob die Eigenschaft auf einen anderen verknüpft ist. Wenn die Eigenschaft verkettet ist, wird die Eigenschaft DBPROP_BOOKMARKS auf `True`. Anhang C der OLE DB-Spezifikation enthält Informationen zu Eigenschaften. Diese Informationen darüber hinaus erfahren Sie, ob die Eigenschaft auf einen anderen verkettet ist.

Sie können auch hinzufügen möchten die `IsValidValue` routinemäßige an Ihrem Code. Der Aufruf Vorlagen `IsValidValue` beim Versuch, eine Eigenschaft festzulegen. Sie würden diese Methode überschreiben, wenn eine zusätzliche Verarbeitung erforderlich ist, wenn Sie einen Eigenschaftswert festlegen. Sie können eine dieser Methoden für jeden Eigenschaftensatz verwenden.

## <a name="see-also"></a>Siehe auch

[Erweiterte Anbietertechniken](../../data/oledb/advanced-provider-techniques.md)