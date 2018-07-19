---
title: CMemoryState-Struktur | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CMemoryState
dev_langs:
- C++
helpviewer_keywords:
- CMemoryState structure [MFC]
- memory leaks [MFC], detecting
- detecting memory leaks [MFC]
ms.assetid: 229d9de7-a6f3-4cc6-805b-5a9d9b1bfe1d
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 17da583b770fcab1d682868c38c04e0aa97155dd
ms.sourcegitcommit: 76fd30ff3e0352e2206460503b61f45897e60e4f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/13/2018
ms.locfileid: "39026432"
---
# <a name="cmemorystate-structure"></a>CMemoryState-Struktur
Bietet eine bequeme Möglichkeit zum Erkennen von Speicherverlusten in Ihrem Programm an.  
  
## <a name="syntax"></a>Syntax  
  
```  
struct CMemoryState  
```  
  
## <a name="members"></a>Member  
  
### <a name="public-constructors"></a>Öffentliche Konstruktoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CMemoryState::CMemoryState](#cmemorystate)|Erstellt eine Klasse-ähnliche-Struktur, die Arbeitsspeicher-Prüfpunkte gesteuert.|  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CMemoryState:: Checkpoint](#checkpoint)|Ruft eine Momentaufnahme (Checkpoint) des aktuellen Speicherzustands ab.|  
|[CMemoryState:: Difference](#difference)|Berechnet die Differenz zwischen zwei Objekten des Typs `CMemoryState`.|  
|[CMemoryState](#dumpallobjectssince)|Gibt eine Zusammenfassung aller aktuell zugeordneten Objekte seit einem vorherigen Prüfpunkt.|  
|[CMemoryState:: DumpStatistics](#dumpstatistics)|Gibt Arbeitsspeicher Zuordnung Statistiken für eine `CMemoryState` Objekt.|  
  
## <a name="remarks"></a>Hinweise  
 `CMemoryState` ist eine Struktur, und verfügt nicht über eine Basisklasse.  
  
 Ein "Arbeitsspeicherverlust" tritt auf, wenn Speicher für ein Objekt auf dem Heap reserviert, aber nicht freigegeben werden, wenn es nicht mehr benötigt wird. Solche Speicherverluste können schließlich zu Out-of-Memory-Fehlern führen. Es gibt mehrere Möglichkeiten zum Reservieren und Freigeben von Arbeitsspeicher in Ihrem Programm:  
  
-   Mithilfe der `malloc` /  `free` Funktionsreihe aus der Laufzeit-Bibliothek.  
  
-   Verwenden die Windows-API-Speicherverwaltungsfunktionen `LocalAlloc` /  `LocalFree` und `GlobalAlloc` /  `GlobalFree`.  
  
-   Mit C++ **neue** und **löschen** Operatoren.  
  
 Die `CMemoryState` Diagnose nur erkennen Speicher Speicherverluste verursacht, wenn Speicher belegt, mit der **neue** Operator wird nicht freigegeben mit **löschen**. Die anderen beiden Gruppen von Speicher-Management-Funktionen sind für nicht-C++-Programme und kombinieren sie mit **neue** und **löschen** im selben Programm wird nicht empfohlen. Eine zusätzliche Makro DEBUG_NEW, wird bereitgestellt, um das Ersetzen der **neue** Operator, wenn Sie die Datei und Zeilennummer der nachverfolgung der speicherbelegungen benötigen. DEBUG_NEW wird verwendet, wenn Sie in der Regel verwenden die **neue** Operator.  
  
 Wie bei anderen Diagnose, die `CMemoryState` Diagnose sind nur in Debugversionen des Programms verfügbar. Eine Debugversion müssen die _DEBUG-Konstante definiert.  
  
 Wenn Sie das Programm weist einen Speicherverlust vermuten, können Sie mithilfe der `Checkpoint`, `Difference`, und `DumpStatistics` Funktionen, um den Unterschied zwischen den Speicherzustand (Objekte, die zugeordnet werden) an zwei verschiedenen Punkten in der programmausführung zu ermitteln. Diese Informationen kann bei der Bestimmung, ob eine Funktion aller Objekte bereinigt wird, die sie weist nützlich sein.  
  
 Wenn Sie einfach zu wissen, in dem das Ungleichgewicht bei der Zuordnung und Aufhebung der Zuordnung erfolgt nicht genügend Informationen bereitstellt, können Sie mithilfe der `DumpAllObjectsSince` Funktion, um alle Objekte, die seit des vorherigen Aufrufs von dump `Checkpoint`. Dieser Dump wird die Reihenfolge der Zuordnung, die Quelldatei und die Zeile, in dem das Objekt reserviert wurde (Wenn Sie für die Zuordnung DEBUG_NEW verwenden) und die Ableitung des Objekts, dessen Adresse und ihre Größe. `DumpAllObjectsSince` Ruft auch des Objekts `Dump` Funktion, um Informationen zu den aktuellen Zustand bereitstellen.  
  
 Weitere Informationen zur Verwendung von `CMemoryState` und weitere Diagnosedaten, finden Sie unter [MFC-Anwendungen Debuggen](/visualstudio/debugger/mfc-debugging-techniques).  
  
> [!NOTE]
>  Deklarationen von Objekten des Typs `CMemoryState` und Aufrufen von Memberfunktionen sollten durch Klammern werden `#if defined(_DEBUG)/#endif` Anweisungen. Dadurch wird die Speicherdiagnose nur in Debugversionen des Programms enthalten sein.  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 `CMemoryState`  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** afx.h  
  
##  <a name="checkpoint"></a>  CMemoryState:: Checkpoint  
 Eine Momentaufnahme des Arbeitsspeichers Zusammenfassung und speichert sie in diesem `CMemoryState` Objekt.  
  
```  
void Checkpoint();
```  
  
### <a name="remarks"></a>Hinweise  
 Die `CMemoryState` Memberfunktionen [Unterschied](#difference) und [DumpAllObjectsSince](#dumpallobjectssince) dieser momentaufnahmedaten verwenden.  
  
### <a name="example"></a>Beispiel  
  Siehe das Beispiel für die [CMemoryState](#cmemorystate) Konstruktor.  
  
##  <a name="cmemorystate"></a>  CMemoryState::CMemoryState  
 Erstellt ein leeres `CMemoryState` -Objekt, das von ausgefüllt werden muss, die [Prüfpunkt](#checkpoint) oder [Unterschied](#difference) Member-Funktion.  
  
```  
CMemoryState();
```  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFC_Utilities#18](../../mfc/codesnippet/cpp/cmemorystate-structure_1.cpp)]  
  
##  <a name="difference"></a>  CMemoryState:: Difference  
 Vergleicht zwei `CMemoryState` Objekte aus, und speichert den Unterschied in diesen `CMemoryState` Objekt.  
  
```  
BOOL Difference(
    const CMemoryState& oldState,   
    const CMemoryState& newState);
```  
  
### <a name="parameters"></a>Parameter  
 *oldState*  
 Die anfängliche Speicherzustand gemäß einem `CMemoryState` Prüfpunkt.  
  
 *newState*  
 Die neuen Speicherstatus gemäß einem `CMemoryState` Prüfpunkt.  
  
### <a name="return-value"></a>Rückgabewert  
 Legen Sie ungleich NULL, wenn es sich bei die beiden Speicherzuständen unterschiedlich sind; andernfalls 0.  
  
### <a name="remarks"></a>Hinweise  
 [Prüfpunkt](#checkpoint) muss für jede der beiden Speicherzustandsobjekte Parameter aufgerufen wurden.  
  
### <a name="example"></a>Beispiel  
  Siehe das Beispiel für die [CMemoryState](#cmemorystate) Konstruktor.  
  
##  <a name="dumpallobjectssince"></a>  CMemoryState  
 Ruft die `Dump` -Funktion für alle Objekte eines Typs von Klasse abgeleitet `CObject` , zugewiesen wurden (und werden weiterhin zugeordnet) seit dem letzten [Prüfpunkt](#checkpoint) Aufrufen für dieses `CMemoryState` Objekt.  
  
```  
void DumpAllObjectsSince() const;

 
```  
  
### <a name="remarks"></a>Hinweise  
 Aufrufen von `DumpAllObjectsSince` mit einer nicht initialisierten `CMemoryState` Objektdumps werden alle Objekte, die momentan im Arbeitsspeicher.  
  
### <a name="example"></a>Beispiel  
  Siehe das Beispiel für die [CMemoryState](#cmemorystate) Konstruktor.  
  
##  <a name="dumpstatistics"></a>  CMemoryState:: DumpStatistics  
 Gibt ein Statistikbericht präzise Speicher, aus einer `CMemoryState` -Objekt, das von ausgefüllt wird die [Unterschied](#difference) Member-Funktion.  
  
```  
void DumpStatistics() const;

 
```  
  
### <a name="remarks"></a>Hinweise  
 Der Bericht, der auf gedruckt wird die [AfxDump](diagnostic-services.md#afxdump) Gerät zeigt Folgendes:  
  
 Ein Beispiel für Bericht bietet Informationen über die Anzahl (oder Menge) von:  
  
-   freier Blöcke  
  
-   normale Blöcke  
  
-   CRT-Blöcke  
  
-   Ignorieren von Blöcken  
  
-   Clientblöcke  
  
-   Maximaler Arbeitsspeicher, die von der Anwendung verwendet wird, gleichzeitig (in Byte)  
  
-   Gesamtarbeitsspeicher, der derzeit von der Anwendung (in Byte) verwendet.  
  
 Bei freien Blöcken handelt, die Anzahl der Blöcke, deren Freigabe verzögert wurde, wenn `afxMemDF` wurde `delayFreeMemDF`. Weitere Informationen finden Sie unter [AfxMemDF](diagnostic-services.md#afxmemdf), im Abschnitt "MFC-Makros und Globals". Finden Sie unter [Blocktypen auf dem Debugheap](http://msdn.microsoft.com/db2e7f62-0679-4b39-a23f-26f2c2f407c5) für Weitere Informationen zu diesen Typen zu blockieren.  
  
### <a name="example"></a>Beispiel  
  Der folgende Code platziert werden soll, *Projname*App.cpp. Definieren Sie die folgenden globalen Variablen:  
  
 [!code-cpp[NVC_MFC_Utilities#40](../../mfc/codesnippet/cpp/cmemorystate-structure_2.cpp)]  
  
 In der `InitInstance` funktioniert, fügen Sie die Zeile:  
  
 [!code-cpp[NVC_MFC_Utilities#41](../../mfc/codesnippet/cpp/cmemorystate-structure_3.cpp)]  
  
 Hinzufügen eines ereignishandlers für das `ExitInstance` Funktion, und verwenden Sie den folgenden Code:  
  
 [!code-cpp[NVC_MFC_Utilities#42](../../mfc/codesnippet/cpp/cmemorystate-structure_4.cpp)]  
  
 Sie können die Anwendung jetzt ausführen, im Debugmodus befinden, um die Ausgabe des finden Sie unter den `DumpStatistics` Funktion.  
  
## <a name="see-also"></a>Siehe auch  
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)



