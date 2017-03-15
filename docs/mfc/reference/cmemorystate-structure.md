---
title: CMemoryState Struktur | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
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
translationtype: Machine Translation
ms.sourcegitcommit: 0e0c08ddc57d437c51872b5186ae3fc983bb0199
ms.openlocfilehash: 037c8f075a14346e3428c5e19bfda662c4f3c2b0
ms.lasthandoff: 02/24/2017

---
# <a name="cmemorystate-structure"></a>CMemoryState-Struktur
Bietet eine bequeme Möglichkeit zum Erkennen von Speicherverlusten in Ihrem Programm an.  
  
## <a name="syntax"></a>Syntax  
  
```  
struct CMemoryState  
```  
  
## <a name="members"></a>Mitglieder  
  
### <a name="public-constructors"></a>Öffentliche Konstruktoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CMemoryState::CMemoryState](#cmemorystate)|Erstellt eine Klasse Struktur, die Arbeitsspeicher-Prüfpunkte steuert.|  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CMemoryState:: Checkpoint](#checkpoint)|Ruft eine Momentaufnahme (Checkpoint) des aktuellen Speicherzustands ab.|  
|[CMemoryState](#difference)|Berechnet den Unterschied zwischen zwei Objekten des Typs `CMemoryState`.|  
|[CMemoryState](#dumpallobjectssince)|Gibt eine Zusammenfassung aller aktuell zugeordneten Objekte seit einem vorherigen Prüfpunkt.|  
|[DumpStatistics](#dumpstatistics)|Gibt Arbeitsspeicher Zuordnung Statistiken für eine `CMemoryState` Objekt.|  
  
## <a name="remarks"></a>Hinweise  
 `CMemoryState`ist eine Struktur, und verfügt nicht über eine Basisklasse.  
  
 Ein "Arbeitsspeicherverlust" tritt auf, wenn für ein Objekt wird auf dem Heap reserviert, jedoch nicht freigegeben werden, wenn es nicht mehr benötigt wird. Solche Speicherverluste können schließlich zu Out-of-Memory-Fehlern führen. Es gibt verschiedene Methoden zum Reservieren und Freigeben von Arbeitsspeicher in Ihrem Programm:  
  
-   Mithilfe der `malloc` /  **freien** Funktionsreihe aus der Laufzeit-Bibliothek.  
  
-   Verwenden die Windows-API-Speicherverwaltungsfunktionen **LocalAlloc**/ **LocalFree** und **GlobalAlloc**/ **GlobalFree**.  
  
-   Mithilfe des C++ **neue** und **löschen** Operatoren.  
  
 Die `CMemoryState` Diagnose nur Hilfe Speicherbereiche ermittelt Speicherverluste verursacht, wenn Sie mithilfe der **neue** Operator wird nicht freigegeben mit **löschen**. Die anderen zwei Gruppen von Speicher-Management-Funktionen sind für nicht-c++-Programme und kombinieren sie mit **neue** und **löschen** im selben Programm wird nicht empfohlen. Ein zusätzlicher-Makro `DEBUG_NEW`, dient zum Ersetzen der **neue** Operator, wenn Sie die Datei und Zeilennummer Verfolgung von speicherbelegungen benötigen. `DEBUG_NEW`wird verwendet, wenn Sie in der Regel verwenden die **neue** Operator.  
  
 Wie bei anderen Diagnose der `CMemoryState` Diagnose sind nur in Debugversionen des Programms verfügbar. Benötigen Sie eine Debugversion der **_DEBUG** -Konstante definiert.  
  
 Wenn Sie das Programm weist einen Speicherverlust vermuten, können Sie die `Checkpoint`, **Unterschied**, und `DumpStatistics` Funktionen, um den Unterschied zwischen den Speicherzustand (Objekte reserviert) an zwei verschiedenen Punkten in der Ausführung des Programms zu ermitteln. Diese Informationen kann bestimmen, ob eine Funktion aller Objekte bereinigen ist, den sie zuordnet nützlich sein.  
  
 Wenn das wissen, wo die Diskrepanz in Belegen und auftritt nicht genügend Informationen bereitstellt, können Sie die `DumpAllObjectsSince` Funktion, um alle Objekte, die seit des letzten Aufrufs von dump `Checkpoint`. Das Speicherabbild zeigt die Reihenfolge der Zuordnung, die Quelldatei und die Zeile, in dem das Objekt zugeordnet wurde (bei Verwendung von `DEBUG_NEW` für die Zuordnung), und die Ableitung des Objekts, dessen Adresse und seine Größe. `DumpAllObjectsSince`Ruft auch jedes Objekt `Dump` Funktion, um Informationen zum aktuellen Zustand bereitzustellen.  
  
 Weitere Informationen zur Verwendung von `CMemoryState` und andere Diagnose finden Sie unter [Debuggen MFC-Anwendung](/visualstudio/debugger/mfc-debugging-techniques).  
  
> [!NOTE]
>  Deklarationen von Objekten des Typs `CMemoryState` und Aufrufen von Memberfunktionen sollten durch Klammern werden `#if defined(_DEBUG)/#endif` Richtlinien. Dadurch wird die Speicherdiagnose nur in Debugversionen des Programms aufgenommen werden.  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 `CMemoryState`  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** afx.h  
  
##  <a name="a-namecheckpointa--cmemorystatecheckpoint"></a><a name="checkpoint"></a>CMemoryState:: Checkpoint  
 Erstellt eine Momentaufnahme des Speichers Zusammenfassung und speichert es in diesem `CMemoryState` Objekt.  
  
```  
void Checkpoint();
```  
  
### <a name="remarks"></a>Hinweise  
 Die `CMemoryState` Memberfunktionen [Unterschied](#difference) und [DumpAllObjectsSince](#dumpallobjectssince) Snapshot verwenden.  
  
### <a name="example"></a>Beispiel  
  Siehe das Beispiel für die [CMemoryState](#cmemorystate) Konstruktor.  
  
##  <a name="a-namecmemorystatea--cmemorystatecmemorystate"></a><a name="cmemorystate"></a>CMemoryState::CMemoryState  
 Erstellt ein leeres `CMemoryState` -Objekt, das von muss, in ausgefüllt werden der [Prüfpunkt](#checkpoint) oder [Unterschied](#difference) Member-Funktion.  
  
```  
CMemoryState();
```  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFC_Utilities&18;](../../mfc/codesnippet/cpp/cmemorystate-structure_1.cpp)]  
  
##  <a name="a-namedifferencea--cmemorystatedifference"></a><a name="difference"></a>CMemoryState  
 Vergleicht zwei `CMemoryState` Objekte, dann speichert den Unterschied in diesen `CMemoryState` Objekt.  
  
```  
BOOL Difference(
    const CMemoryState& oldState,   
    const CMemoryState& newState);
```  
  
### <a name="parameters"></a>Parameter  
 *oldState*  
 Die anfängliche Speicherzustand gemäß einer `CMemoryState` Prüfpunkt.  
  
 *newState*  
 Die neuen Speicherstatus wie definiert eine `CMemoryState` Prüfpunkt.  
  
### <a name="return-value"></a>Rückgabewert  
 Wert ungleich NULL, wenn die beiden Speicherzustände unterscheiden; andernfalls 0.  
  
### <a name="remarks"></a>Hinweise  
 [Prüfpunkt](#checkpoint) müssen für jede der beiden Speicherzustandsobjekte Parameter aufgerufen wurden.  
  
### <a name="example"></a>Beispiel  
  Siehe das Beispiel für die [CMemoryState](#cmemorystate) Konstruktor.  
  
##  <a name="a-namedumpallobjectssincea--cmemorystatedumpallobjectssince"></a><a name="dumpallobjectssince"></a>CMemoryState  
 Ruft die `Dump` -Funktion für alle Objekte eines Typs von Klasse abgeleitet `CObject` , die zugeordnet wurden (und dennoch zugeordnet sind) seit dem letzten [Prüfpunkt](#checkpoint) Aufrufen für dieses `CMemoryState` Objekt.  
  
```  
void DumpAllObjectsSince() const;

 
```  
  
### <a name="remarks"></a>Hinweise  
 Aufrufen von `DumpAllObjectsSince` mit einer nicht initialisierten `CMemoryState` Objektdumps werden alle Objekte, die momentan im Arbeitsspeicher.  
  
### <a name="example"></a>Beispiel  
  Siehe das Beispiel für die [CMemoryState](#cmemorystate) Konstruktor.  
  
##  <a name="a-namedumpstatisticsa--cmemorystatedumpstatistics"></a><a name="dumpstatistics"></a>DumpStatistics  
 Druckt einen präzise Arbeitsspeicher Statistikbericht aus einer `CMemoryState` -Objekt, das von ausgefüllt wird die [Unterschied](#difference) Member-Funktion.  
  
```  
void DumpStatistics() const;

 
```  
  
### <a name="remarks"></a>Hinweise  
 Der Bericht, der auf die [AfxDump](http://msdn.microsoft.com/library/4b3cfa3f-fb75-456a-9d99-a5601acbcb11) Gerät, wird Folgendes angezeigt:  
  
 Ein Beispiel für Bericht bietet Informationen über die Anzahl oder den Betrag der:  
  
-   freier Blöcke  
  
-   normale Blöcke  
  
-   CRT-Blöcke  
  
-   Blöcke zu ignorieren  
  
-   Clientblöcke  
  
-   Maximaler Arbeitsspeicher, die von der Anwendung verwendet werden, gleichzeitig (in Byte)  
  
-   Gesamtspeicher, die derzeit von der Anwendung (in Byte) verwendet.  
  
 Bei freien Blöcken handelt, die Anzahl der Blöcke, deren Freigabe verzögert wurde, wenn `afxMemDF` wurde **DelayFreeMemDF**. Weitere Informationen finden Sie unter [AfxMemDF](diagnostic-services.md#afxmemdf), im Abschnitt "MFC-Makros und Globals". Finden Sie unter [Blocktypen auf dem Debugheap](http://msdn.microsoft.com/en-us/db2e7f62-0679-4b39-a23f-26f2c2f407c5) für Weitere Informationen zu diesen Typen gesperrt.  
  
### <a name="example"></a>Beispiel  
  Der folgende Code platziert werden sollte, *Projektname*App.cpp. Definieren Sie die folgenden globalen Variablen:  
  
 [!code-cpp[NVC_MFC_Utilities&#40;](../../mfc/codesnippet/cpp/cmemorystate-structure_2.cpp)]  
  
 In der `InitInstance` Funktion, fügen Sie die Zeile:  
  
 [!code-cpp[NVC_MFC_Utilities&#41;](../../mfc/codesnippet/cpp/cmemorystate-structure_3.cpp)]  
  
 Fügen Sie einen Ereignishandler für das `ExitInstance` funktionieren, und verwenden Sie den folgenden Code:  
  
 [!code-cpp[NVC_MFC_Utilities&#42;](../../mfc/codesnippet/cpp/cmemorystate-structure_4.cpp)]  
  
 Sie können jetzt das Programm im Debugmodus, um die Ausgabe des finden Sie unter Ausführen der `DumpStatistics` Funktion.  
  
## <a name="see-also"></a>Siehe auch  
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)




