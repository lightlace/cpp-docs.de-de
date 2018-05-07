---
title: Übergeben von OLE DB-Konformitätstests | Microsoft Docs
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
ms.openlocfilehash: 11677e6295956de768c7ebc0c113d775b066bb0c
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="passing-ole-db-conformance-tests"></a>Erfolgreiche Durchführung der OLE DB-Konformitätstests
Damit Anbieter mehr Konsistenz erzielt, bietet das Data Access SDK eine Reihe von OLE DB-Konformitätstests. Die Tests überprüfen Sie alle Aspekte des Anbieters ein, und geben Ihnen die Sicherheit, die der Anbieter erwartungsgemäß funktioniert. Sie können den OLE DB-Konformitätstests finden, auf das Microsoft Data Access SDK. Dieser Abschnitt konzentriert sich auf Dinge, die Sie ausführen sollten, um die Konformitätstests besteht. Informationen zum Ausführen der OLE DB-Konformitätstests finden Sie im SDK.  
  
## <a name="running-the-conformance-tests"></a>Ausführen der Konformitätstests  
 In Visual C++ 6.0 hinzugefügt der OLE DB-Anbietervorlagen diverse Verbinden von Funktionen, die Eigenschaften und Werte überprüfen können. Die meisten dieser Funktionen, die als Antwort auf die Konformitätstests hinzugefügt wurden.  
  
> [!NOTE]
>  Sie müssen mehrere Validierungsfunktionen für Ihren Anbieter für OLE DB-Konformitätstests besteht hinzufügen.  
  
 Diese Anbieter sind zwei Validierungsroutinen erforderlich. Die erste Routine `CRowsetImpl::ValidateCommandID`, ist Teil der Rowsetklasse. Er wird während der Erstellung des Rowsets von den Anbietervorlagen aufgerufen. Das Beispiel verwendet diese Routine, um Consumern mitzuteilen, dass sie die Indizes nicht unterstützt. Der erste Aufruf `CRowsetImpl::ValidateCommandID` (Beachten Sie, die der Anbieter verwendet die **_RowsetBaseClass** Typedef, die in die schnittstellenzuordnung für hinzugefügt `CMyProviderRowset` in [Anbieterunterstützung für Lesezeichen](../../data/oledb/provider-support-for-bookmarks.md), sodass Sie nicht auf Geben Sie diese lange Zeile Vorlagenargumente). Als Nächstes zurückgeben **DB_E_NOINDEX** Indexparameter ist nicht **NULL** (das heißt, möchte, dass der Consumer einen Index verwenden). Weitere Informationen über die Befehls-IDs finden Sie in der OLE DB-Spezifikation, und suchen Sie nach **IOpenRowset:: OPENROWSET**.  
  
 Der folgende Code ist die **ValidateCommandID** Validierungsroutine:  
  
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
  
 Die Anbietervorlagen rufen die `OnPropertyChanged` -Methode auf, wenn jemand auf eine Eigenschaft ändert die **DBPROPSET_ROWSET** Gruppe. Wenn Sie Eigenschaften für die anderen Gruppen behandeln möchten, fügen Sie sie in das entsprechende Objekt (d. h. **DBPROPSET_SESSION** Überprüfungen wechseln Sie der `CMyProviderSession` Klasse).  
  
 Der Code überprüft zuerst, ob die Eigenschaft auf einen anderen verknüpft ist. Wenn die Eigenschaft verkettet ist, wird die **DBPROP_BOOKMARKS** Eigenschaft auf "true". Anhang C der OLE DB-Spezifikation enthält Informationen zu Eigenschaften. Diese Informationen darüber hinaus erfahren Sie, ob die Eigenschaft an einen anderen Konstruktor verkettet ist.  
  
 Sie können auch hinzufügen möchten die `IsValidValue` routinemäßige für Ihren Code. Der Aufruf Vorlagen `IsValidValue` beim Versuch, eine Eigenschaft festzulegen. Sie würden diese Methode überschreiben, wenn Sie zusätzliche Verarbeitung erforderlich, beim Festlegen eines Eigenschaftswerts ist. Sie können eine der folgenden Methoden für jeden Eigenschaftensatz verwenden.  
  
## <a name="threading-issues"></a>Threadingprobleme  
 Standardmäßig generiert der OLE DB-Anbieterassistent im ATL-OLE DB-Anbieter-Assistenten Code für den Anbieter in einem Apartmentmodell ausgeführt. Wenn Sie versuchen, diesen Code in den Konformitätstests auszuführen, erhalten Sie zunächst Fehlern. Dies ist da Ltm.exe, das Tool verwendet, um den OLE DB-Konformitätstests frei ist standardmäßig eine Singlethreadsitzung handelt. Der OLE DB-Anbieter-Assistenten Code standardmäßig Apartmentmodell für Leistung und benutzerfreundlichkeit.  
  
 Um dieses Problem zu beheben, können Sie LTM ändern oder den Anbieter ändern.  
  
#### <a name="to-change-ltm-to-run-in-apartment-threaded-mode"></a>Zum Ändern der LTM im Apartment ausgeführt Singlethread-Modus  
  
1.  Klicken Sie im Hauptmenü LTM auf **Tools**, und klicken Sie dann auf **Optionen**.  
  
2.  Auf der **allgemeine** ändern das Threadingmodell aus **freien Thread** auf **Apartment Threaded**.  
  
 So ändern Sie Ihren Anbieter im Singlethread Modus "free" ausführen:  
  
-   Suchen Sie in Ihrem Anbieterprojekt für alle Instanzen von `CComSingleThreadModel` und ersetzen es durch `CComMultiThreadModel`, die in Ihrer Data Source, Session und Rowset Headern sein sollte.  
  
-   Ändern Sie in der RGS-Datei des Threadingmodells aus **Apartment** auf **beide**.  
  
-   Führen Sie richtige Programmierung Regeln kostenlos Singlethread-Programmierung (d. h. Sperren bei Schreibvorgängen).  
  
## <a name="see-also"></a>Siehe auch  
 [Erweiterte Anbietertechniken](../../data/oledb/advanced-provider-techniques.md)