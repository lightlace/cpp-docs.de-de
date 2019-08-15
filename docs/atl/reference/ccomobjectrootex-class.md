---
title: CComObjectRootEx-Klasse
ms.date: 11/04/2016
f1_keywords:
- CComObjectRootEx
- ATLCOM/ATL::CComObjectRootEx
- ATLCOM/ATL::InternalAddRef
- ATLCOM/ATL::InternalRelease
- ATLCOM/ATL::Lock
- ATLCOM/ATL::Unlock
- ATLCOM/ATL::FinalConstruct
- ATLCOM/ATL::FinalRelease
- ATLCOM/ATL::OuterAddRef
- ATLCOM/ATL::OuterQueryInterface
- ATLCOM/ATL::OuterRelease
- ATLCOM/ATL::InternalQueryInterface
- ATLCOM/ATL::ObjectMain
- ATLCOM/ATL::m_dwRef
- ATLCOM/ATL::m_pOuterUnknown
helpviewer_keywords:
- reference counting
ms.assetid: 894a3d7c-2daf-4fd0-8fa4-e6a05bcfb631
ms.openlocfilehash: 8fa4e7a035ded2e1a20dd278a5d54d40252e1958
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/15/2019
ms.locfileid: "69497050"
---
# <a name="ccomobjectrootex-class"></a>CComObjectRootEx-Klasse

Diese Klasse stellt Methoden bereit, um die Verwaltung der Objekt Verweis Zählung sowohl für nicht aggregierte als auch für aggregierte Objekte zu behandeln.

## <a name="syntax"></a>Syntax

```
template<class ThreadModel>
class CComObjectRootEx : public CComObjectRootBase
```

#### <a name="parameters"></a>Parameter

*ThreadModel*<br/>
Die Klasse, deren Methoden das gewünschte Threading Modell implementieren. Sie können das Threading Modell explizit auswählen, indem Sie *threadmodel* auf " [CComSingleThreadModel](../../atl/reference/ccomsinglethreadmodel-class.md)", " [CComMultiThreadModel](../../atl/reference/ccommultithreadmodel-class.md)" oder " [ccommultithreadmodelnocs](../../atl/reference/ccommultithreadmodelnocs-class.md)" festlegen. Sie können das Standard Thread Modell des Servers akzeptieren, indem Sie *threadmodel* auf [ccomobjectthreadmodel](atl-typedefs.md#ccomobjectthreadmodel) oder [ccomglobalsthread Model](atl-typedefs.md#ccomglobalsthreadmodel)festlegen.

## <a name="members"></a>Member

### <a name="methods"></a>Methoden

|||
|-|-|
|[CComObjectRootEx](#ccomobjectrootex)|Konstruktor.|
|[InternalAddRef](#internaladdref)|Inkremente den Verweis Zähler für ein nicht aggregiertes Objekt.|
|[InternalRelease](#internalrelease)|Dekremente den Verweis Zähler für ein nicht aggregiertes Objekt.|
|[Sperre](#lock)|Wenn das Thread Modell Multithreaded ist, erhält den Besitz eines kritischen Abschnitts Objekts.|
|[Entsperren](#unlock)|Wenn das Thread Modell Multithreaded ist, gibt den Besitz eines kritischen Abschnitts Objekts frei.|

### <a name="ccomobjectrootbase-methods"></a>Ccomobjectrootbase-Methoden

|||
|-|-|
|[FinalConstruct](#finalconstruct)|Überschreiben Sie in der-Klasse, um alle für Ihr Objekt erforderlichen Initialisierungen auszuführen.|
|[FinalRelease](#finalrelease)|Überschreiben Sie in der-Klasse, um alle für Ihr Objekt erforderlichen Bereinigungs Vorgänge auszuführen.|
|[OuterAddRef](#outeraddref)|Erhöht den Verweis Zähler für ein aggregiertes Objekt.|
|[OuterQueryInterface](#outerqueryinterface)|Delegiert an den äußeren `IUnknown` eines aggregierten Objekts.|
|[Outerrelease](#outerrelease)|Dekremente den Verweis Zähler für ein aggregiertes Objekt.|

### <a name="static-functions"></a>Statische Funktionen

|||
|-|-|
|[InternalQueryInterface](#internalqueryinterface)|Delegiert an den `IUnknown` eines nicht aggregierten Objekts.|
|[ObjectMain](#objectmain)|Wird während der Initialisierung und Beendigung von Modulen für abgeleitete Klassen aufgerufen, die in der Objekt Zuordnung aufgeführt sind.|

### <a name="data-members"></a>Datenmember

|||
|-|-|
|[m_dwRef](#m_dwref)|Mit `m_pOuterUnknown`, Teil einer Union. Wird verwendet, wenn das Objekt nicht aggregiert wird, um den Verweis `AddRef` Zähler `Release`von und zu speichern.|
|[m_pOuterUnknown](#m_pouterunknown)|Mit `m_dwRef`, Teil einer Union. Wird verwendet, wenn das Objekt aggregiert wird, um einen Zeiger auf das äußere unbekannte festzuhalten.|

## <a name="remarks"></a>Hinweise

`CComObjectRootEx`behandelt die Verwaltung von Objekt Verweis zählungs Punkten für nicht aggregierte und aggregierte Objekte. Sie enthält den Objekt Verweis Zähler, wenn das Objekt nicht aggregiert wird, und enthält den Zeiger auf das äußere unbekannte, wenn das Objekt aggregiert wird. Bei aggregierten Objekten `CComObjectRootEx` können Methoden verwendet werden, um den Fehler des inneren Objekts zu verarbeiten und das äußere Objekt vor dem Löschen zu schützen, wenn innere Schnittstellen freigegeben oder das innere Objekt gelöscht wird.

Eine Klasse, die einen com-Server implementiert, `CComObjectRootEx` muss von oder [CComObjectRoot](../../atl/reference/ccomobjectroot-class.md)erben.

Wenn die Klassendefinition das [DECLARE_POLY_AGGREGATABLE](aggregation-and-class-factory-macros.md#declare_poly_aggregatable) -Makro angibt, erstellt ATL eine Instanz `CComPolyObject<CYourClass>` von `IClassFactory::CreateInstance` , wenn aufgerufen wird. Während der Erstellung wird der Wert des äußeren unbekannten-Werts geprüft. Wenn er NULL ist, `IUnknown` wird für ein nicht aggregiertes Objekt implementiert. Wenn das äußere unbekannte nicht NULL ist, `IUnknown` wird für ein aggregiertes Objekt implementiert.

Wenn die Klasse das DECLARE_POLY_AGGREGATABLE-Makro nicht angibt, erstellt ATL eine Instanz von `CAggComObject<CYourClass>` für aggregierte Objekte oder eine Instanz von `CComObject<CYourClass>` für nicht aggregierte Objekte.

Der Vorteil der Verwendung `CComPolyObject` von besteht darin, dass Sie `CComAggObject` vermeiden `CComObject` , dass sowohl als auch in Ihrem Modul die aggregierten und nicht aggregierten Fälle verarbeiten. Ein einzelnes `CComPolyObject` -Objekt behandelt beide Fälle. Daher ist nur eine Kopie der vtable und eine Kopie der Funktionen in Ihrem Modul vorhanden. Wenn Ihre Vtable groß ist, kann dies die Modulgröße erheblich verringern. Wenn die Vtable jedoch klein ist, kann die `CComPolyObject` Verwendung von zu einer etwas größeren Modulgröße führen, da Sie nicht für ein aggregiertes oder nicht aggregiertes Objekt `CComAggObject` wie und `CComObject`optimiert ist.

Wenn das Objekt aggregiert wird, wird [IUnknown](/windows/win32/api/unknwn/nn-unknwn-iunknown) von `CComAggObject` oder `CComPolyObject`implementiert. Diese Klassen delegieren `QueryInterface` `AddRef` `CComObjectRootEx`die-, `Release` `OuterQueryInterface`- und-`OuterRelease` Aufrufe von, und an den äußeren unbekannten. `OuterAddRef` In der Regel über `CComObjectRootEx::FinalConstruct` schreiben Sie in der-Klasse, um aggregierte Objekte zu `CComObjectRootEx::FinalRelease` erstellen, und überschreiben, um alle aggregierten Objekte freizugeben.

Wenn das Objekt nicht aggregiert wird, `IUnknown` wird von `CComObject` oder `CComPolyObject`implementiert. In diesem Fall werden Aufrufe von `QueryInterface`, `AddRef`und `Release` an `CComObjectRootEx`die `InternalQueryInterface` `InternalAddRef` ,`InternalRelease` und delegiert, um die eigentlichen Vorgänge auszuführen.

## <a name="requirements"></a>Anforderungen

**Header:** Atlcom. h

##  <a name="ccomobjectrootex"></a>CComObjectRootEx:: CComObjectRootEx

Der-Konstruktor initialisiert den Verweis Zähler auf 0.

```
CComObjectRootEx();
```

##  <a name="finalconstruct"></a>CComObjectRootEx:: FinalConstruct

Sie können diese Methode in der abgeleiteten Klasse überschreiben, um die für Ihr Objekt erforderliche Initialisierung auszuführen.

```
HRESULT FinalConstruct();
```

### <a name="return-value"></a>Rückgabewert

Rückgabe von "S_OK" bei Erfolg oder einem der Standardfehler-HRESULT-Werte.

### <a name="remarks"></a>Hinweise

Standardmäßig `CComObjectRootEx::FinalConstruct` gibt S_OK einfach zurück.

Die Initialisierung wird in `FinalConstruct` anstelle des Konstruktors der Klasse durchgeführt:

- Sie können keinen Statuscode von einem Konstruktor zurückgeben, Sie können jedoch ein HRESULT mit `FinalConstruct`dem Rückgabewert zurückgeben. Wenn Objekte der Klasse mit der standardmäßigen Klassenfactory von ATL erstellt werden, wird dieser Rückgabewert zurück an den com-Client weitergegeben, sodass Sie ausführliche Fehlerinformationen bereitstellen können.

- Virtuelle Funktionen können nicht über den Mechanismus der virtuellen Funktion aus dem Konstruktor einer Klasse aufgerufen werden. Das Aufrufen einer virtuellen Funktion aus dem Konstruktor einer Klasse führt zu einem statisch aufgelösten Aufruf der Funktion, wie Sie an diesem Punkt in der Vererbungs Hierarchie definiert ist. Aufrufe von reinen virtuellen Funktionen führen zu Linker-Fehlern.

   Die Klasse ist nicht die am meisten abgeleitete Klasse in der Vererbungs Hierarchie – Sie basiert auf einer von ATL bereitgestellten abgeleiteten Klasse, um einige Funktionen bereitzustellen. Es besteht die Möglichkeit, dass Ihre Initialisierung die von dieser Klasse bereitgestellten Funktionen verwendet (Dies trifft sicherlich zu, wenn Objekte Ihrer Klasse andere Objekte aggregieren müssen), aber der Konstruktor in der Klasse hat keine Möglichkeit, auf diese Funktionen zuzugreifen. Der Konstruktions Code für die Klasse wird ausgeführt, bevor die am meisten abgeleitete Klasse vollständig konstruiert ist.

   Wird jedoch `FinalConstruct` sofort aufgerufen, nachdem die am meisten abgeleitete Klasse vollständig konstruiert wurde, sodass Sie virtuelle Funktionen aufrufen und die von ATL bereitgestellte Implementierung der Verweis Zählung verwenden können.

### <a name="example"></a>Beispiel

Überschreiben Sie diese Methode in der Regel in der `CComObjectRootEx` von abgeleiteten Klasse, um aggregierte Objekte zu erstellen. Beispiel:

[!code-cpp[NVC_ATL_COM#40](../../atl/codesnippet/cpp/ccomobjectrootex-class_1.h)]

Wenn die Konstruktion fehlschlägt, können Sie einen Fehler zurückgeben. Sie können auch das Makro [DECLARE_PROTECT_FINAL_CONSTRUCT](aggregation-and-class-factory-macros.md#declare_protect_final_construct) verwenden, um das Löschen des äußeren Objekts vor dem Löschen zu schützen, wenn das interne aggregierte Objekt während der Erstellung den Verweis Zähler Inkremente erhöht und dann die Anzahl auf 0 verringert.

Im folgenden finden Sie eine typische Möglichkeit zum Erstellen eines Aggregats:

- Fügen Sie `IUnknown` dem Klassenobjekt einen Zeiger hinzu, und initialisieren Sie ihn im Konstruktor mit NULL.

- Über `FinalConstruct` schreiben, um das Aggregat zu erstellen.

- Verwenden Sie `IUnknown` den Zeiger, den Sie als Parameter für das [COM_INTERFACE_ENTRY_AGGREGATE](com-interface-entry-macros.md#com_interface_entry_aggregate) -Makro definiert haben.

- Über `FinalRelease` schreiben, um `IUnknown` den Zeiger freizugeben.

##  <a name="finalrelease"></a>CComObjectRootEx:: FinalRelease

Sie können diese Methode in der abgeleiteten Klasse überschreiben, um alle für Ihr Objekt erforderlichen Bereinigungs Vorgänge auszuführen.

```
void FinalRelease();
```

### <a name="remarks"></a>Hinweise

Standardmäßig `CComObjectRootEx::FinalRelease` wird von nichts unterstützt.

Das Ausführen von Bereinigung in `FinalRelease` ist besser als das Hinzufügen von Code zum Dekonstruktor ihrer Klasse, da das Objekt noch vollständig an dem Punkt, an dem aufgerufen wird, `FinalRelease` vollständig konstruiert ist. Dies ermöglicht den sicheren Zugriff auf die Methoden, die von der am weitesten abgeleiteten Klasse bereitgestellt werden. Dies ist besonders wichtig für das Freigeben von aggregierten Objekten vor dem Löschen.

##  <a name="internaladdref"></a>CComObjectRootEx:: internaladressf

Erhöht den Verweis Zähler eines nicht aggregierten Objekts um 1.

```
ULONG InternalAddRef();
```

### <a name="return-value"></a>Rückgabewert

Ein Wert, der für die Diagnose und das Testen nützlich sein kann.

### <a name="remarks"></a>Hinweise

Wenn das Thread Modell Multithreaded ist, `InterlockedIncrement` wird verwendet, um zu verhindern, dass mehrere Threads gleichzeitig den Verweis Zähler ändern.

##  <a name="internalqueryinterface"></a>CComObjectRootEx:: InternalQueryInterface

Ruft einen Zeiger auf die angeforderte Schnittstelle ab.

```
static HRESULT InternalQueryInterface(
    void* pThis,
    const _ATL_INTMAP_ENTRY* pEntries,
    REFIID iid,
    void** ppvObject);
```

### <a name="parameters"></a>Parameter

*pThis*<br/>
in Ein Zeiger auf das-Objekt, das die com-Zuordnung der Schnitt `QueryInterface`stellen enthält, die für verfügbar sind.

*pentries*<br/>
in Ein Zeiger auf die `_ATL_INTMAP_ENTRY` -Struktur, die auf eine Karte der verfügbaren Schnittstellen zugreift.

*iid*<br/>
in Der GUID der angeforderten Schnittstelle.

*ppvObject*<br/>
vorgenommen Ein Zeiger auf den in *IID*angegebenen Schnittstellen Zeiger oder NULL, wenn die Schnittstelle nicht gefunden wurde.

### <a name="return-value"></a>Rückgabewert

Einer der HRESULT-Standardwerte.

### <a name="remarks"></a>Hinweise

`InternalQueryInterface`behandelt nur Schnittstellen in der com-Zuordnungs Tabelle. Wenn das Objekt aggregiert wird, `InternalQueryInterface` delegiert nicht an das äußere unbekannte. Sie können Schnittstellen in die com-Zuordnungs Tabelle mit dem Makro [COM_INTERFACE_ENTRY](com-interface-entry-macros.md#com_interface_entry) oder einer der Varianten eingeben.

##  <a name="internalrelease"></a>CComObjectRootEx:: internalrelease

Dekremente den Verweis Zähler eines nicht aggregierten Objekts um 1.

```
ULONG InternalRelease();
```

### <a name="return-value"></a>Rückgabewert

In nicht-Debug-und Debugbuilds gibt diese Funktion einen Wert zurück, der möglicherweise für Diagnose-oder Testzwecke nützlich ist. Der genaue zurückgegebene Wert hängt von vielen Faktoren ab, wie z. b. dem verwendeten Betriebssystem, und möglicherweise dem Verweis Zähler.

### <a name="remarks"></a>Hinweise

Wenn das Thread Modell Multithreaded ist, `InterlockedDecrement` wird verwendet, um zu verhindern, dass mehrere Threads gleichzeitig den Verweis Zähler ändern.

##  <a name="lock"></a>CComObjectRootEx:: Lock

Wenn das Thread Modell Multithreaded ist, ruft diese Methode die Win32-API-Funktion " [EnterCriticalSection](/windows/win32/api/synchapi/nf-synchapi-entercriticalsection)" auf, die wartet, bis der Thread den Besitz des kritischen Abschnitts Objekts übernimmt, das über ein privates Datenmember abgerufen wurde.

```
void Lock();
```

### <a name="remarks"></a>Hinweise

Wenn die Ausführung des geschützten Codes abgeschlossen ist, muss der `Unlock` Thread aufzurufen, um den Besitz des kritischen Abschnitts freizugeben.

Wenn das Thread Modell Single Thread ist, führt diese Methode keine Aktion aus.

##  <a name="m_dwref"></a>CComObjectRootEx:: m_dwRef

Ein Teil einer Union, der auf vier Byte Arbeitsspeicher zugreift.

```
long m_dwRef;
```

### <a name="remarks"></a>Hinweise

Mit `m_pOuterUnknown`einem Teil einer Union:

```
union {
    long m_dwRef;
    IUnknown* m_pOuterUnknown;
};
```

Wenn das Objekt nicht aggregiert wird, wird der Verweis Zähler, `AddRef` auf `Release` den und zugreifen `m_dwRef`, in gespeichert. Wenn das Objekt aggregiert wird, wird der Zeiger auf das äußere unbekannte in [m_pOuterUnknown](#m_pouterunknown)gespeichert.

##  <a name="m_pouterunknown"></a>CComObjectRootEx:: m_pOuterUnknown

Ein Teil einer Union, der auf vier Byte Arbeitsspeicher zugreift.

```
IUnknown*
    m_pOuterUnknown;
```

### <a name="remarks"></a>Hinweise

Mit `m_dwRef`einem Teil einer Union:

```
union {
    long m_dwRef;
    IUnknown* m_pOuterUnknown;
};
```

Wenn das Objekt aggregiert wird, wird der Zeiger auf das äußere unbekannte in `m_pOuterUnknown`gespeichert. Wenn das Objekt nicht aggregiert wird, wird der Verweis Zähler, `AddRef` auf `Release` den und zugreifen, in [m_dwRef](#m_dwref)gespeichert.

##  <a name="objectmain"></a>CComObjectRootEx:: objectmain

Für jede Klasse, die in der Objekt Zuordnung aufgeführt ist, wird diese Funktion einmal aufgerufen, wenn das Modul initialisiert wird, und wenn Sie beendet wird.

```
static void WINAPI ObjectMain(bool bStarting);
```

### <a name="parameters"></a>Parameter

*bStarting*<br/>
vorgenommen Der Wert ist "true", wenn die Klasse initialisiert wird. andernfalls false.

### <a name="remarks"></a>Hinweise

Der Wert des *bstarting* -Parameters gibt an, ob das Modul initialisiert oder beendet wird. Die Standard Implementierung von `ObjectMain` führt keine Aktion aus, aber Sie können diese Funktion in der Klasse überschreiben, um Ressourcen zu initialisieren oder zu bereinigen, die Sie für die Klasse zuordnen möchten. Beachten Sie `ObjectMain` , dass aufgerufen wird, bevor Instanzen der-Klasse angefordert werden.

`ObjectMain`wird vom Einstiegspunkt der dll aufgerufen, sodass der Typ des Vorgangs, der von der Einstiegspunkt Funktion durchgeführt werden kann, eingeschränkt ist. Weitere Informationen zu diesen Einschränkungen finden Sie unter [DLLs und Verhalten C++ der visuellen Lauf Zeit Bibliothek](../../build/run-time-library-behavior.md) und [DllMain](/windows/win32/Dlls/dllmain).

### <a name="example"></a>Beispiel

[!code-cpp[NVC_ATL_COM#41](../../atl/codesnippet/cpp/ccomobjectrootex-class_2.h)]

##  <a name="outeraddref"></a>CComObjectRootEx:: outeradressf

Inkremente den Verweis Zähler des äußeren unbekannten einer Aggregation.

```
ULONG OuterAddRef();
```

### <a name="return-value"></a>Rückgabewert

Ein Wert, der für die Diagnose und das Testen nützlich sein kann.

##  <a name="outerqueryinterface"></a>CComObjectRootEx:: outerqueryinterface

Ruft einen indirekten Zeiger auf die angeforderte Schnittstelle ab.

```
HRESULT OuterQueryInterface(REFIID iid, void** ppvObject);
```

### <a name="parameters"></a>Parameter

*iid*<br/>
in Der GUID der angeforderten Schnittstelle.

*ppvObject*<br/>
vorgenommen Ein Zeiger auf den in *IID*angegebenen Schnittstellen Zeiger oder NULL, wenn die Aggregation die-Schnittstelle nicht unterstützt.

### <a name="return-value"></a>Rückgabewert

Einer der HRESULT-Standardwerte.

##  <a name="outerrelease"></a>CComObjectRootEx:: outerrelease

Dekremente den Verweis Zähler des äußeren unbekannten einer Aggregation.

```
ULONG OuterRelease();
```

### <a name="return-value"></a>Rückgabewert

In nicht Debugbuilds gibt immer 0 zurück. In Debugbuilds gibt einen Wert zurück, der für die Diagnose oder das Testen nützlich sein kann.

##  <a name="unlock"></a>CComObjectRootEx:: Unlock

Wenn das Thread Modell Multithreaded ist, ruft diese Methode die Win32-API-Funktion [LeaveCriticalSection](/windows/win32/api/synchapi/nf-synchapi-leavecriticalsection)auf, die den Besitz des kritischen Abschnitts Objekts freigibt, das über ein privates Datenmember abgerufen wird.

```
void Unlock();
```

### <a name="remarks"></a>Hinweise

Der Thread muss aufgerufen `Lock`werden, um den Besitz zu erhalten. Jeder-Befehl `Unlock` erfordert einen entsprechenden-Befehl, um den Besitz des kritischen Abschnitts freizugeben. `Lock`

Wenn das Thread Modell Single Thread ist, führt diese Methode keine Aktion aus.

## <a name="see-also"></a>Siehe auch

[CComAggObject-Klasse](../../atl/reference/ccomaggobject-class.md)<br/>
[CComObject-Klasse](../../atl/reference/ccomobject-class.md)<br/>
[CComPolyObject-Klasse](../../atl/reference/ccompolyobject-class.md)<br/>
[Klassen Übersicht](../../atl/atl-class-overview.md)
