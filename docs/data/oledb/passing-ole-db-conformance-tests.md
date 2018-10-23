---
title: Übergeben von OLE DB-Konformitätstests | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- testing, OLE DB providers
- testing providers
- conformance testing
- conformance testing [OLE DB]
- OLE DB providers, testing
ms.assetid: d1a4f147-2edd-476c-b452-0e6a0ac09891
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 70607e0518d13015ee11895270ad3306cd3da24b
ms.sourcegitcommit: 0164af5615389ffb1452ccc432eb55f6dc931047
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/23/2018
ms.locfileid: "49808172"
---
# <a name="passing-ole-db-conformance-tests"></a>Erfolgreiche Durchführung der OLE DB-Konformitätstests

Um Anbieter konsistenter zu machen, bietet der Data Access SDK einen Satz von OLE DB-Konformitätstests. Die Tests überprüfen Sie alle Aspekte des Anbieters ein, und geben Ihnen die Sicherheit, die der Anbieter erwartungsgemäß funktioniert. Der OLE DB-Konformitätstests finden Sie auf der Microsoft Data Access SDK. Dieser Abschnitt konzentriert sich auf Dinge, die Sie tun sollten, um die Konformitätstests besteht. Informationen zum Ausführen der OLE DB-Konformitätstests finden Sie im SDK.  
  
## <a name="running-the-conformance-tests"></a>Ausführen der Konformitätstests  

In Visual C++ 6.0 hinzugefügt, die OLE DB-Anbietervorlagen eine Reihe von hooking Funktionen, die Ihnen ermöglichen, Werte und Eigenschaften zu überprüfen. Die meisten dieser Funktionen wurden als Reaktion auf die Konformitätstests hinzugefügt.  
  
> [!NOTE]
> Sie müssen mehrere Validierungsfunktionen für Ihren Anbieter, um die OLE DB-Konformitätstests besteht hinzufügen.  
  
Der Anbieter erfordert zwei Überprüfungsroutinen. Die erste Routine, `CRowsetImpl::ValidateCommandID`, ist Teil der Rowsetklasse. Es wird während der Erstellung des Rowsets von die Anbietervorlagen aufgerufen werden. Das Beispiel verwendet diese Routine, um Consumern mitzuteilen, dass sie die Indizes nicht unterstützt. Der erste Aufruf `CRowsetImpl::ValidateCommandID` (Beachten Sie, die der Anbieter verwendet die `_RowsetBaseClass` Typedef, die hinzugefügt werden, in die schnittstellenzuordnung für `CMyProviderRowset` in [Anbieterunterstützung für Lesezeichen](../../data/oledb/provider-support-for-bookmarks.md), sodass Sie nicht, lange Zeile in der Vorlage eingeben (Argumente). Als Nächstes DB_E_NOINDEX zurückgegeben, wenn der Indexparameter nicht NULL ist (das heißt, möchte, dass der Consumer einen Index verwenden). Weitere Informationen zu den Befehls-IDs finden Sie in der OLE DB-Spezifikation, und suchen Sie nach `IOpenRowset::OpenRowset`.  
  
Der folgende Code ist die `ValidateCommandID` Validierungsroutine:  
  
```cpp
/////////////////////////////////////////////////////////////////////  
// MyProviderRS.H  
// Class: CMyProviderRowset   
  
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
  
Die Anbietervorlagen rufen die `OnPropertyChanged` -Methode auf, wenn jemand auf eine Eigenschaft ändert die `DBPROPSET_ROWSET` Gruppe. Sollten Sie die Eigenschaften für andere Gruppen zu behandeln, fügen Sie sie in das entsprechende Objekt (d. h. `DBPROPSET_SESSION` Überprüfungen wechseln Sie der `CMyProviderSession` Klasse).  
  
Der Code überprüft zuerst, um festzustellen, ob die Eigenschaft auf einen anderen verknüpft ist. Wenn die Eigenschaft verkettet ist, wird die `DBPROP_BOOKMARKS` Eigenschaft `True`. Anhang C der OLE DB-Spezifikation enthält Informationen zu Eigenschaften. Diese Informationen darüber hinaus erfahren Sie, ob die Eigenschaft auf einen anderen verkettet ist.  
  
Sie können auch hinzufügen möchten die `IsValidValue` routinemäßige an Ihrem Code. Der Aufruf Vorlagen `IsValidValue` beim Versuch, eine Eigenschaft festzulegen. Sie würden diese Methode überschreiben, wenn eine zusätzliche Verarbeitung erforderlich ist, wenn Sie einen Eigenschaftswert festlegen. Sie können eine dieser Methoden für jeden Eigenschaftensatz verwenden.  
  
## <a name="see-also"></a>Siehe auch  

[Erweiterte Anbietertechniken](../../data/oledb/advanced-provider-techniques.md)