---
title: CMemoryState Struktur | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CMemoryState
dev_langs:
- C++
helpviewer_keywords:
- CMemoryState structure
- memory leaks, detecting
- detecting memory leaks
ms.assetid: 229d9de7-a6f3-4cc6-805b-5a9d9b1bfe1d
caps.latest.revision: 19
author: mikeblome
ms.author: mblome
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
ms.translationtype: Machine Translation
ms.sourcegitcommit: bb94e24657d16b2a3eda3a770c2b6ae734c6006f
ms.openlocfilehash: 5485a3cf8107dd9b245cb2d3fff6982f31279abe
ms.contentlocale: de-de
ms.lasthandoff: 04/12/2017

---
# <a name="cmemorystate-structure"></a>CMemoryState-Struktur
Bietet eine einfache Möglichkeit zum Erkennen von Speicherverlusten in Ihrem Programm an.  
  
## <a name="syntax"></a>Syntax  
  
```  
struct CMemoryState  
```  
  
## <a name="members"></a>Mitglieder  
  
### <a name="public-constructors"></a>Öffentliche Konstruktoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CMemoryState::CMemoryState](#cmemorystate)|Erstellt eine Klasse-ähnliche-Struktur, die Arbeitsspeicher-Prüfpunkte steuert.|  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CMemoryState:: Checkpoint](#checkpoint)|Ruft eine Momentaufnahme (Checkpoint) des aktuellen Speicherzustands ab.|  
|[CMemoryState](#difference)|Berechnet den Unterschied zwischen zwei Objekten des Typs `CMemoryState`.|  
|[CMemoryState](#dumpallobjectssince)|Gibt einen Überblick über alle derzeit zugeordneten Objekte seit einem vorherigen Prüfpunkt.|  
|[DumpStatistics](#dumpstatistics)|Gibt Arbeitsspeicher Zuordnung Statistiken für eine `CMemoryState` Objekt.|  
  
## <a name="remarks"></a>Hinweise  
 `CMemoryState`ist eine Struktur, und verfügt nicht über eine Basisklasse.  
  
 "Arbeitsspeicherverlust" tritt auf, wenn der Speicher für ein Objekt auf dem Heap belegt, jedoch nicht freigegeben werden, wenn es nicht mehr benötigt wird. Solche Speicherverluste können schließlich zu Out-of-Memory-Fehlern führen. Es gibt verschiedene Methoden zum Belegen und Freigeben von Arbeitsspeicher in Ihrem Programm:  
  
-   Mithilfe der `malloc` /  **freien** Funktionsreihe aus der Laufzeit-Bibliothek.  
  
-   Mithilfe der Windows-API-Speicherverwaltungsfunktionen **LocalAlloc**/ **LocalAlloc** und **GlobalAlloc**/ **GlobalFree**.  
  
-   Mithilfe des C++ **neue** und **löschen** Operatoren.  
  
 Die `CMemoryState` erkennen Arbeitsspeicher nur bei der Diagnose prüfen auf Speicherverluste verursacht, wenn Speicherplatz belegt mithilfe der **neue** Operator wird aufgehoben, wenn mit **löschen**. Die anderen zwei Gruppen von Speicher-Management-Funktionen sind für nicht C++-Programmen und kombinieren sie mit **neue** und **löschen** im selben Programm wird nicht empfohlen. Eine zusätzliche Makro `DEBUG_NEW`, wird bereitgestellt, um das Ersetzen der **neue** Operator, wenn Sie die Datei und die Nummer der Zeile Track für speicherbelegungen benötigen. `DEBUG_NEW`wird verwendet, wenn Sie normalerweise verwenden die **neue** Operator.  
  
 Wie bei anderen Diagnose der `CMemoryState` Diagnose sind nur in Debugversionen des Programms verfügbar. Eine Debugversion benötigen die **_DEBUG** definierte Konstante.  
  
 Wenn Sie vermuten, das Programm weist einen Speicherverlust dass, können Sie die `Checkpoint`, **Unterschied**, und `DumpStatistics` Funktionen, um den Unterschied zwischen den Speicherzustand (Objekte, die zugeordnet werden) an zwei verschiedenen Punkten in der Ausführung des Programms zu ermitteln. Diese Informationen können hilfreich bei der Bestimmung, ob eine Funktion aller Objekte bereinigt wird er reserviert sein.  
  
 Wenn Sie einfach zu wissen, wo die Diskrepanz in der Zuordnung und Aufhebung der Zuordnung tritt auf, nicht genügend Informationen bereitstellt, können Sie mithilfe der `DumpAllObjectsSince` Funktion, um alle Objekte, die seit des letzten Aufrufs von dump `Checkpoint`. Das Speicherabbild zeigt die Reihenfolge der Zuordnung, die Quelldatei und das Liniendiagramm, in dem das Objekt zugeordnet wurde (bei Verwendung von `DEBUG_NEW` für die Zuordnung), und die Ableitung des Objekts, dessen Adresse und seine Größe. `DumpAllObjectsSince`Ruft auch jedes Objekt `Dump` Funktion, um Informationen zum aktuellen Zustand bereitzustellen.  
  
 Weitere Informationen zur Verwendung von `CMemoryState` und andere Diagnose finden Sie unter [MFC-Anwendungen Debuggen](/visualstudio/debugger/mfc-debugging-techniques).  
  
> [!NOTE]
>  Deklarationen von Objekten des Typs `CMemoryState` und Aufrufen von Memberfunktionen sollten durch Klammern werden `#if defined(_DEBUG)/#endif` Direktiven. Dies bewirkt, dass die Speicherdiagnose, nur in Debugversionen des Programms eingeschlossen werden sollen.  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 `CMemoryState`  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** afx.h  
  
##  <a name="checkpoint"></a>CMemoryState:: Checkpoint  
 Erstellt eine Momentaufnahme Zusammenfassung des Arbeitsspeichers und speichert sie in diesem `CMemoryState` Objekt.  
  
```  
void Checkpoint();
```  
  
### <a name="remarks"></a>Hinweise  
 Die `CMemoryState` Memberfunktionen [Unterschied](#difference) und [DumpAllObjectsSince](#dumpallobjectssince) dieser momentaufnahmedaten verwenden.  
  
### <a name="example"></a>Beispiel  
  Siehe das Beispiel für die [CMemoryState](#cmemorystate) Konstruktor.  
  
##  <a name="cmemorystate"></a>CMemoryState::CMemoryState  
 Erstellt ein leeres `CMemoryState` -Objekt, das von muss, in ausgefüllt werden der [Prüfpunkt](#checkpoint) oder [Unterschied](#difference) Memberfunktion.  
  
```  
CMemoryState();
```  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFC_Utilities Nr. 18](../../mfc/codesnippet/cpp/cmemorystate-structure_1.cpp)]  
  
##  <a name="difference"></a>CMemoryState  
 Vergleicht zwei `CMemoryState` Objekte, und speichert den Unterschied in diese `CMemoryState` Objekt.  
  
```  
BOOL Difference(
    const CMemoryState& oldState,   
    const CMemoryState& newState);
```  
  
### <a name="parameters"></a>Parameter  
 *oldState*  
 Die anfängliche Speicherzustands gemäß der Definition von einer `CMemoryState` Prüfpunkt.  
  
 *newState*  
 Die neuen Speicherstatus gemäß Definition durch eine `CMemoryState` Prüfpunkt.  
  
### <a name="return-value"></a>Rückgabewert  
 Wert ungleich NULL, wenn die beiden Speicherzustände unterscheiden; andernfalls 0.  
  
### <a name="remarks"></a>Hinweise  
 [Prüfpunkt](#checkpoint) muss für jeden der zwei Speicherzustands Parameter aufgerufen wurde.  
  
### <a name="example"></a>Beispiel  
  Siehe das Beispiel für die [CMemoryState](#cmemorystate) Konstruktor.  
  
##  <a name="dumpallobjectssince"></a>CMemoryState  
 Ruft die `Dump` Funktion für alle Objekte eines Typs, die von Klasse abgeleitet `CObject` , die zugeordnet wurden (und dennoch zugeordnet sind) seit dem letzten [Prüfpunkt](#checkpoint) Aufrufen für dieses `CMemoryState` Objekt.  
  
```  
void DumpAllObjectsSince() const;

 
```  
  
### <a name="remarks"></a>Hinweise  
 Aufrufen von `DumpAllObjectsSince` mit einer nicht initialisierten `CMemoryState` Objektdumps werden alle Objekte, die momentan im Arbeitsspeicher.  
  
### <a name="example"></a>Beispiel  
  Siehe das Beispiel für die [CMemoryState](#cmemorystate) Konstruktor.  
  
##  <a name="dumpstatistics"></a>DumpStatistics  
 Druckt einen präzise Arbeitsspeicher Statistikbericht aus einer `CMemoryState` -Objekt, das von ausgefüllt wird die [Unterschied](#difference) Memberfunktion.  
  
```  
void DumpStatistics() const;

 
```  
  
### <a name="remarks"></a>Hinweise  
 Der Bericht gedruckt wird die [AfxDump](diagnostic-services.md#afxdump) Gerät zeigt Folgendes:  
  
 Ein Beispiel für Bericht bietet Informationen hinsichtlich der Anzahl (oder Menge) von:  
  
-   freier Blöcke  
  
-   normale Blöcke  
  
-   CRT-Blöcke  
  
-   Blöcke zu ignorieren  
  
-   Clientblöcke  
  
-   Maximaler Arbeitsspeicher, die von der Anwendung verwendet werden, jeweils (in Bytes)  
  
-   vom Programm (in Bytes) derzeit verwendeten Gesamtarbeitsspeicher  
  
 Bei freien Blöcken handelt, die Anzahl der Blöcke, deren Freigabe verzögert wurde, wenn `afxMemDF` wurde **DelayFreeMemDF**. Weitere Informationen finden Sie unter [AfxMemDF](diagnostic-services.md#afxmemdf), im Abschnitt "MFC-Makros und Globals". Finden Sie unter [Blocktypen auf dem Debugheap](http://msdn.microsoft.com/en-us/db2e7f62-0679-4b39-a23f-26f2c2f407c5) für Weitere Informationen zu diesen Typen zu blockieren.  
  
### <a name="example"></a>Beispiel  
  Der folgende Code sollte *Projname*App.cpp. Definieren Sie die folgenden globalen Variablen:  
  
 [!code-cpp[NVC_MFC_Utilities #-40](../../mfc/codesnippet/cpp/cmemorystate-structure_2.cpp)]  
  
 In der `InitInstance` -Funktion, fügen Sie die Zeile:  
  
 [!code-cpp[NVC_MFC_Utilities #41](../../mfc/codesnippet/cpp/cmemorystate-structure_3.cpp)]  
  
 Fügen Sie einen Handler für das `ExitInstance` Funktion, und verwenden Sie den folgenden Code:  
  
 [!code-cpp[NVC_MFC_Utilities #42](../../mfc/codesnippet/cpp/cmemorystate-structure_4.cpp)]  
  
 Sie können die Anwendung jetzt ausführen, im Debugmodus befinden, um die Ausgabe des finden Sie unter der `DumpStatistics` Funktion.  
  
## <a name="see-also"></a>Siehe auch  
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)




