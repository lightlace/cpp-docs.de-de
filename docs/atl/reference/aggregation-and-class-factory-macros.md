---
title: Aggregation und Klassenfactory-Makros | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: reference
f1_keywords:
- atlcom/ATL::DECLARE_AGGREGATABLE
- atlcom/ATL::DECLARE_CLASSFACTORY
- atlcom/ATL::DECLARE_CLASSFACTORY_EX
- atlcom/ATL::DECLARE_CLASSFACTORY_AUTO_THREAD
- atlcom/ATL::DECLARE_CLASSFACTORY_SINGLETON
- atlcom/ATL::DECLARE_GET_CONTROLLING_UNKNOWN
- atlcom/ATL::DECLARE_NOT_AGGREGATABLE
- atlcom/ATL::DECLARE_ONLY_AGGREGATABLE
- atlcom/ATL::DECLARE_POLY_AGGREGATABLE
- atlcom/ATL::DECLARE_PROTECT_FINAL_CONSTRUCT
- atlcom/ATL::DECLARE_VIEW_STATUS
dev_langs:
- C++
helpviewer_keywords:
- class factories, ATL macros
- aggregation [C++], ATL macros
ms.assetid: d99d379a-0eec-481f-8daa-252dac18f163
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: ba2c1b96a1ce4db7c16695c51d946ecb98827271
ms.sourcegitcommit: 92dbc4b9bf82fda96da80846c9cfcdba524035af
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/05/2018
ms.locfileid: "43752787"
---
# <a name="aggregation-and-class-factory-macros"></a>Aggregation und Klassenfactory-Makros

Diese Makros bieten Möglichkeiten zum Steuern der Aggregation und Klassenfactorys zu deklarieren.

|||
|-|-|
|[DECLARE_AGGREGATABLE](#declare_aggregatable)|Gibt an, dass das Objekt sein kann (Standard) aggregiert.|
|[DECLARE_CLASSFACTORY](#declare_classfactory)|Deklariert die Klassenfactory sein [CComClassFactory](../../atl/reference/ccomclassfactory-class.md), die ATL-Standard-Klassenfactory.|
|[DECLARE_CLASSFACTORY_EX](#declare_classfactory_ex)|Deklariert die Ihre Klassenfactoryobjekt soll die Klassenfactory.|
|[DECLARE_CLASSFACTORY2](#declare_classfactory2)|Deklariert [CComClassFactory2](../../atl/reference/ccomclassfactory2-class.md) soll die Klassenfactory.|
|[DECLARE_CLASSFACTORY_AUTO_THREAD](#declare_classfactory_auto_thread)|Deklariert [CComClassFactoryAutoThread](../../atl/reference/ccomclassfactoryautothread-class.md) soll die Klassenfactory.|
|[DECLARE_CLASSFACTORY_SINGLETON](#declare_classfactory_singleton)|Deklariert [CComClassFactorySingleton](../../atl/reference/ccomclassfactorysingleton-class.md) soll die Klassenfactory.|
|[DECLARE_GET_CONTROLLING_UNKNOWN](#declare_get_controlling_unknown)|Deklariert eine virtuelle `GetControllingUnknown` Funktion.|
|[DECLARE_NOT_AGGREGATABLE](#declare_not_aggregatable)|Deklariert, dass das Objekt nicht aggregiert werden kann.|
|[DECLARE_ONLY_AGGREGATABLE](#declare_only_aggregatable)|Deklariert, dass das Objekt aggregiert werden muss.|
|[DECLARE_POLY_AGGREGATABLE](#declare_poly_aggregatable)|Überprüft den Wert der äußeren unbekannten und das Objekt deklariert, aggregiert oder nicht aggregierbar, je nach Bedarf.|
|[DECLARE_PROTECT_FINAL_CONSTRUCT](#declare_protect_final_construct)|Schützt das äußere Objekt vor dem Löschen, während der Erstellung eines inneren Objekts.|
|[DECLARE_VIEW_STATUS](#declare_view_status)|Gibt die VIEWSTATUS Flags in den Container.|  

## <a name="requirements"></a>Anforderungen

**Header:** atlcom.h

##  <a name="declare_aggregatable"></a>  DECLARE_AGGREGATABLE

Gibt an, dass das Objekt aggregiert werden kann.

```
DECLARE_AGGREGATABLE( x )
```

### <a name="parameters"></a>Parameter

*w*  
[in] Der Name der Klasse, die Sie als aggregierbar definieren.

### <a name="remarks"></a>Hinweise

[CComCoClass](../../atl/reference/ccomcoclass-class.md) enthält dieses Makro, um das Standardmodell für die Aggregation anzugeben. Um diese Standardeinstellung zu überschreiben, geben Sie entweder die [DECLARE_NOT_AGGREGATABLE](#declare_not_aggregatable) oder [DECLARE_ONLY_AGGREGATABLE](#declare_only_aggregatable) Makro in der Klassendefinition.

### <a name="example"></a>Beispiel

[!code-cpp[NVC_ATL_Windowing#121](../../atl/codesnippet/cpp/aggregation-and-class-factory-macros_1.h)]

##  <a name="declare_classfactory"></a>  DECLARE_CLASSFACTORY

Deklariert [CComClassFactory](../../atl/reference/ccomclassfactory-class.md) soll die Klassenfactory.

```
DECLARE_CLASSFACTORY()
```

### <a name="remarks"></a>Hinweise

[CComCoClass](../../atl/reference/ccomcoclass-class.md) dieses Makro verwendet, um die Standard-Klassenfactory für Ihr Objekt deklarieren.

### <a name="example"></a>Beispiel

[!code-cpp[NVC_ATL_COM#55](../../atl/codesnippet/cpp/aggregation-and-class-factory-macros_2.h)]

##  <a name="ccomclassfactory_class"></a>  CComClassFactory-Klasse

Diese Klasse implementiert die [IClassFactory](/windows/desktop/api/unknwnbase/nn-unknwnbase-iclassfactory) Schnittstelle.

```
class CComClassFactory : public IClassFactory,
public CComObjectRootEx<CComGlobalsThreadModel>
```

### <a name="remarks"></a>Hinweise

`CComClassFactory` implementiert die [IClassFactory](/windows/desktop/api/unknwnbase/nn-unknwnbase-iclassfactory) -Schnittstelle, die Methoden zum Erstellen eines Objekts von einer bestimmten CLSID als auch die Klassenfactory im Arbeitsspeicher, um neue Objekte schneller erstellt werden können Sperren enthält. `IClassFactory` muss für jede Klasse implementiert werden, die Sie in der Registrierung und Zuweisen von dem Sie eine CLSID registrieren.

ATL-Objekte abrufen eine Klassenfactory normalerweise durch Ableiten von [CComCoClass](../../atl/reference/ccomcoclass-class.md). Diese Klasse enthält das Makro [DECLARE_CLASSFACTORY](#declare_classfactory), die deklariert wird, `CComClassFactory` als der Standardklassenfactory. Um diese Standardeinstellung zu überschreiben, geben Sie einen von der DECLARE_CLASSFACTORY*XXX* Makros in der Klassendefinition. Z. B. die [DECLARE_CLASSFACTORY_EX](#declare_classfactory_ex) Makro verwendet die angegebene Klasse für die Klassenfactory:

[!code-cpp[NVC_ATL_COM#8](../../atl/codesnippet/cpp/aggregation-and-class-factory-macros_3.h)]

Die oben genannten Klassendefinition gibt an, dass `CMyClassFactory` als Standardklassenfactory des Objekts verwendet wird. `CMyClassFactory` muss abgeleitet `CComClassFactory` und überschreiben `CreateInstance`.

ATL stellt drei andere Makros, die eine Klassenfactory zu deklarieren:

- [DECLARE_CLASSFACTORY2](#declare_classfactory2) verwendet [CComClassFactory2](../../atl/reference/ccomclassfactory2-class.md), welche Steuerelemente erstellen, die über eine Lizenz.

- [DECLARE_CLASSFACTORY_AUTO_THREAD](#declare_classfactory_auto_thread) verwendet [CComClassFactoryAutoThread](../../atl/reference/ccomclassfactoryautothread-class.md), die Objekte in mehreren Apartments erstellt.

- [DECLARE_CLASSFACTORY_SINGLETON](#declare_classfactory_singleton) verwendet [CComClassFactorySingleton](../../atl/reference/ccomclassfactorysingleton-class.md), die eine einzelne erstellt [CComObjectGlobal](../../atl/reference/ccomobjectglobal-class.md) Objekt.

##  <a name="declare_classfactory_ex"></a>  DECLARE_CLASSFACTORY_EX

Deklariert `cf` soll die Klassenfactory.

```
DECLARE_CLASSFACTORY_EX( cf )
```

### <a name="parameters"></a>Parameter

*CF*  
[in] Der Name der Klasse, die Ihre Klasse-Factoryobjekt implementiert.

### <a name="remarks"></a>Hinweise

Die *Cf* Parameter ableiten muss [CComClassFactory](../../atl/reference/ccomclassfactory-class.md) und überschreiben die `CreateInstance` Methode.

[CComCoClass](../../atl/reference/ccomcoclass-class.md) enthält die [DECLARE_CLASSFACTORY](#declare_classfactory) Makro, das gibt `CComClassFactory` als der Standardklassenfactory. Das Makro DECLARE_CLASSFACTORY_EX in die Definition der Klasse des Objekts einschließen, überschreiben Sie jedoch diese Standardeinstellung.

### <a name="example"></a>Beispiel

[!code-cpp[NVC_ATL_COM#8](../../atl/codesnippet/cpp/aggregation-and-class-factory-macros_3.h)]

##  <a name="declare_classfactory2"></a>  DECLARE_CLASSFACTORY2

Deklariert [CComClassFactory2](../../atl/reference/ccomclassfactory2-class.md) soll die Klassenfactory.

```
DECLARE_CLASSFACTORY2( lic )
```

### <a name="parameters"></a>Parameter

*LIC*  
[in] Eine Klasse, die implementiert `VerifyLicenseKey`, `GetLicenseKey`, und `IsLicenseValid`.

### <a name="remarks"></a>Hinweise

[CComCoClass](../../atl/reference/ccomcoclass-class.md) enthält die [DECLARE_CLASSFACTORY](#declare_classfactory) Makro, das gibt [CComClassFactory](../../atl/reference/ccomclassfactory-class.md) als der Standardklassenfactory. Das Makro DECLARE_CLASSFACTORY2 in die Definition der Klasse des Objekts einschließen, überschreiben Sie jedoch diese Standardeinstellung.

### <a name="example"></a>Beispiel

[!code-cpp[NVC_ATL_COM#2](../../atl/codesnippet/cpp/aggregation-and-class-factory-macros_4.h)]

##  <a name="ccomclassfactory2_class"></a>  CComClassFactory2-Klasse

Diese Klasse implementiert die [IClassFactory2](/windows/desktop/api/ocidl/nn-ocidl-iclassfactory2) Schnittstelle.

```
template <class license>
class  CComClassFactory2 : public IClassFactory2,
    public CComObjectRootEx<CComGlobalsThreadModel>,
    public license
```

### <a name="parameters"></a>Parameter

*Lizenz*  
Eine Klasse, die folgenden statischen Funktionen implementiert:

- `static BOOL VerifyLicenseKey( BSTR bstr );`

- `static BOOL GetLicenseKey( DWORD dwReserved, BSTR * pBstr );`

- `static BOOL IsLicenseValid( );`

### <a name="remarks"></a>Hinweise

`CComClassFactory2` implementiert die [IClassFactory2](/windows/desktop/api/ocidl/nn-ocidl-iclassfactory2) -Schnittstelle, die eine Erweiterung der [IClassFactory](/windows/desktop/api/unknwnbase/nn-unknwnbase-iclassfactory). `IClassFactory2` Steuerelemente Objekt-und Arrayerstellung über eine Lizenz. Eine Klasse Factory ausführen auf einem lizenzierten Computer kann einen Laufzeit-Lizenzschlüssel bereitstellen. Diesen Lizenzschlüssel kann es sich um eine Anwendung, um Objekte zu instanziieren, wenn eine Lizenz des gesamten Computers nicht vorhanden ist.

ATL-Objekte abrufen eine Klassenfactory normalerweise durch Ableiten von [CComCoClass](../../atl/reference/ccomcoclass-class.md). Diese Klasse enthält das Makro [DECLARE_CLASSFACTORY](#declare_classfactory), die deklariert wird, [CComClassFactory](../../atl/reference/ccomclassfactory-class.md) als der Standardklassenfactory. Verwendung von `CComClassFactory2`, geben Sie die [DECLARE_CLASSFACTORY2](#declare_classfactory2) Makro in der Definition der Klasse des Objekts. Zum Beispiel:

[!code-cpp[NVC_ATL_COM#2](../../atl/codesnippet/cpp/aggregation-and-class-factory-macros_4.h)]

`CMyLicense`, der Vorlagenparameter `CComClassFactory2`, müssen die statischen Funktionen implementieren `VerifyLicenseKey`, `GetLicenseKey`, und `IsLicenseValid`. Im folgenden finden ein Beispiel für eine einfache Lizenz-Klasse:

[!code-cpp[NVC_ATL_COM#3](../../atl/codesnippet/cpp/aggregation-and-class-factory-macros_5.h)]

`CComClassFactory2` leitet sich von sowohl `CComClassFactory2Base` und *Lizenz*. `CComClassFactory2Base`, leitet sich wiederum von `IClassFactory2` und **CComObjectRootEx\< CComGlobalsThreadModel >**.

##  <a name="declare_classfactory_auto_thread"></a>  DECLARE_CLASSFACTORY_AUTO_THREAD

Deklariert [CComClassFactoryAutoThread](../../atl/reference/ccomclassfactoryautothread-class.md) soll die Klassenfactory.

```
DECLARE_CLASSFACTORY_AUTO_THREAD()
```

### <a name="remarks"></a>Hinweise

[CComCoClass](../../atl/reference/ccomcoclass-class.md) enthält die [DECLARE_CLASSFACTORY](#declare_classfactory) Makro, das gibt [CComClassFactory](../../atl/reference/ccomclassfactory-class.md) als der Standardklassenfactory. Das Makro DECLARE_CLASSFACTORY_AUTO_THREAD in die Definition der Klasse des Objekts einschließen, überschreiben Sie jedoch diese Standardeinstellung.

Wenn Sie Objekte in mehreren-Apartments (in einem Out-of-Proc-Server) erstellen, fügen Sie DECLARE_CLASSFACTORY_AUTO_THREAD Ihrer Klasse hinzu.

### <a name="example"></a>Beispiel

[!code-cpp[NVC_ATL_COM#9](../../atl/codesnippet/cpp/aggregation-and-class-factory-macros_6.h)]

##  <a name="ccomclassfactoryautothread_class"></a>  CComClassFactoryAutoThread-Klasse

Diese Klasse implementiert die [IClassFactory](/windows/desktop/api/unknwnbase/nn-unknwnbase-iclassfactory) Schnittstelle und ermöglicht es Objekten, die in mehreren Apartments erstellt werden.

> [!IMPORTANT]
>  Diese Klasse und ihre Member können nicht in Anwendungen verwendet werden, die in der Windows-Runtime ausgeführt werden.

```
class CComClassFactoryAutoThread : public IClassFactory,
public CComObjectRootEx<CComGlobalsThreadModel>
```

### <a name="remarks"></a>Hinweise

`CComClassFactoryAutoThread` ist vergleichbar mit [CComClassFactory](../../atl/reference/ccomclassfactory-class.md), sondern ermöglicht es Objekten, die in mehreren Apartments erstellt werden. Um diese Unterstützung nutzen zu können, leiten Sie Ihre EXE-Modul aus [CComAutoThreadModule](../../atl/reference/ccomautothreadmodule-class.md).

ATL-Objekte abrufen eine Klassenfactory normalerweise durch Ableiten von [CComCoClass](../../atl/reference/ccomcoclass-class.md). Diese Klasse enthält das Makro [DECLARE_CLASSFACTORY](#declare_classfactory), die deklariert wird, [CComClassFactory](../../atl/reference/ccomclassfactory-class.md) als der Standardklassenfactory. Verwendung von `CComClassFactoryAutoThread`, geben Sie die [DECLARE_CLASSFACTORY_AUTO_THREAD](#declare_classfactory_auto_thread) Makro in der Definition der Klasse des Objekts. Zum Beispiel:

[!code-cpp[NVC_ATL_COM#9](../../atl/codesnippet/cpp/aggregation-and-class-factory-macros_6.h)]

##  <a name="declare_classfactory_singleton"></a>  DECLARE_CLASSFACTORY_SINGLETON

Deklariert [CComClassFactorySingleton](../../atl/reference/ccomclassfactorysingleton-class.md) soll die Klassenfactory.

```
DECLARE_CLASSFACTORY_SINGLETON( obj )
```

### <a name="parameters"></a>Parameter

*obj*  
[in] Der Name des Klassenobjekts.

### <a name="remarks"></a>Hinweise

[CComCoClass](../../atl/reference/ccomcoclass-class.md) enthält die [DECLARE_CLASSFACTORY](#declare_classfactory) Makro, das gibt [CComClassFactory](../../atl/reference/ccomclassfactory-class.md) als der Standardklassenfactory. Das Makro DECLARE_CLASSFACTORY_SINGLETON in die Definition der Klasse des Objekts einschließen, überschreiben Sie jedoch diese Standardeinstellung.

### <a name="example"></a>Beispiel

[!code-cpp[NVC_ATL_COM#10](../../atl/codesnippet/cpp/aggregation-and-class-factory-macros_7.h)]

##  <a name="ccomclassfactorysingleton_class"></a>  CComClassFactorySingleton-Klasse

Diese Klasse wird von [CComClassFactory](../../atl/reference/ccomclassfactory-class.md) und verwendet [CComObjectGlobal](../../atl/reference/ccomobjectglobal-class.md) um ein einzelnes Objekt zu erstellen.

> [!IMPORTANT]
>  Diese Klasse und ihre Member können nicht in Anwendungen verwendet werden, die in der Windows-Runtime ausgeführt werden.

```
template<class T>
class CComClassFactorySingleton : public CComClassFactory
```

### <a name="parameters"></a>Parameter

*T*  
Die Klasse.

`CComClassFactorySingleton` leitet sich von [CComClassFactory](../../atl/reference/ccomclassfactory-class.md) und verwendet [CComObjectGlobal](../../atl/reference/ccomobjectglobal-class.md) um ein einzelnes Objekt zu erstellen. Jeder Aufruf der `CreateInstance` -Methode fragt einfach dieses Objekt für einen Schnittstellenzeiger auf.

### <a name="remarks"></a>Hinweise

ATL-Objekte abrufen eine Klassenfactory normalerweise durch Ableiten von [CComCoClass](../../atl/reference/ccomcoclass-class.md). Diese Klasse enthält das Makro [DECLARE_CLASSFACTORY](#declare_classfactory), die deklariert wird, `CComClassFactory` als der Standardklassenfactory. Verwendung von `CComClassFactorySingleton`, geben Sie die [DECLARE_CLASSFACTORY_SINGLETON](#declare_classfactory_singleton) Makro in der Definition der Klasse des Objekts. Zum Beispiel:

[!code-cpp[NVC_ATL_COM#10](../../atl/codesnippet/cpp/aggregation-and-class-factory-macros_7.h)]

##  <a name="declare_get_controlling_unknown"></a>  DECLARE_GET_CONTROLLING_UNKNOWN

Deklariert eine virtuelle Funktion `GetControllingUnknown`.

```
DECLARE_GET_CONTROLLING_UNKNOWN()
```

### <a name="remarks"></a>Hinweise

Dieses Makro auf Ihr Objekt hinzufügen, wenn Sie die Fehlermeldung des Compilers erhalten `GetControllingUnknown` ist nicht definiert (z. B. in `CComAggregateCreator`).

##  <a name="declare_not_aggregatable"></a>  DECLARE_NOT_AGGREGATABLE

Gibt an, dass das Objekt kann nicht aggregiert werden.

```
DECLARE_NOT_AGGREGATABLE( x )
```

### <a name="parameters"></a>Parameter

*w*  
[in] Der Name des Klassenobjekts, die Sie als nicht aggregierbar definieren.

### <a name="remarks"></a>Hinweise

Bewirkt, dass DECLARE_NOT_AGGREGATABLE `CreateInstance` auf Fehler (CLASS_E_NOAGGREGATION) zurück, wenn versucht wird zum Aggregieren auf das Objekt.

In der Standardeinstellung [CComCoClass](../../atl/reference/ccomcoclass-class.md) enthält die [DECLARE_AGGREGATABLE](#declare_aggregatable) Makro, das gibt an, dass das Objekt aggregiert werden kann. Um dieses Standardverhalten zu überschreiben, enthalten Sie DECLARE_NOT_AGGREGATABLE in der Klassendefinition ein.

### <a name="example"></a>Beispiel

[!code-cpp[NVC_ATL_Windowing#121](../../atl/codesnippet/cpp/aggregation-and-class-factory-macros_1.h)]

##  <a name="declare_only_aggregatable"></a>  DECLARE_ONLY_AGGREGATABLE

Gibt an, dass das Objekt aggregiert werden muss.

```
DECLARE_ONLY_AGGREGATABLE( x )
```

### <a name="parameters"></a>Parameter

*w*  
[in] Der Name des Klassenobjekts, die Sie als nur aggregierbar definieren.

### <a name="remarks"></a>Hinweise

DECLARE_ONLY_AGGREGATABLE verursacht einen Fehler (E_FAIL) aus, wenn es sich bei dem Versuch, `CoCreate` das Objekt als zusammengesetzten Objekt.

In der Standardeinstellung [CComCoClass](../../atl/reference/ccomcoclass-class.md) enthält die [DECLARE_AGGREGATABLE](#declare_aggregatable) Makro, das gibt an, dass das Objekt aggregiert werden kann. Um dieses Standardverhalten zu überschreiben, enthalten Sie DECLARE_ONLY_AGGREGATABLE in der Klassendefinition ein.

### <a name="example"></a>Beispiel

[!code-cpp[NVC_ATL_Windowing#125](../../atl/codesnippet/cpp/aggregation-and-class-factory-macros_8.h)]

##  <a name="declare_poly_aggregatable"></a>  DECLARE_POLY_AGGREGATABLE

Gibt an, dass eine Instanz von **CComPolyObject \<**  *x* **>** wird erstellt, wenn das Objekt erstellt wird.

```
DECLARE_POLY_AGGREGATABLE( x )
```

### <a name="parameters"></a>Parameter

*w*  
[in] Der Name des Klassenobjekts, die Sie als aggregiert oder als nicht aggregierbar definieren.

### <a name="remarks"></a>Hinweise

Während der Erstellung wird der Wert, der die äußere unbekannte überprüft. Wenn auf NULL, `IUnknown` für einen zusammengesetzten Objekt implementiert wird. Wenn die äußere unbekannte ungleich NULL ist `IUnknown` wird für ein zusammengesetztes Objekt implementiert.

Der Vorteil der Verwendung von DECLARE_POLY_AGGREGATABLE ist, dass Sie vermeiden, dass beide `CComAggObject` und `CComObject` innerhalb des Moduls, die aggregierte und zusammengesetzten Fälle zu behandeln. Ein einzelnes `CComPolyObject` Objekt behandelt beide Fälle. Dies bedeutet, dass nur eine Kopie der Vtable und eine Kopie der Funktionen, die innerhalb des Moduls vorhanden sind. Wenn Ihre Vtable groß ist, kann dies Modulgröße erheblich verringern. Die Vtable klein ist, jedoch verwenden `CComPolyObject` kann dazu führen, etwas Modul größer, da sie nicht für ein Objekt zusammengesetzten oder aggregiert, optimiert ist wie `CComAggObject` und `CComObject`.

Das Makro DECLARE_POLY_AGGREGATABLE wird automatisch in das Objekt deklariert, bei Verwendung von ATL-Steuerelement-Assistenten, um eine vollständige Kontrolle zu erstellen.

##  <a name="declare_protect_final_construct"></a>  DECLARE_PROTECT_FINAL_CONSTRUCT

Verhindert, dass das Objekt gelöscht wird, wenn (während der [FinalConstruct](ccomobjectrootex-class.md#finalconstruct)) internen aggregierten Objekts erhöht die verweiszählung wird verringert die Anzahl auf 0.

```
DECLARE_PROTECT_FINAL_CONSTRUCT()
```

##  <a name="declare_view_status"></a>  DECLARE_VIEW_STATUS

Platzieren Sie dieses Makro in der Steuerelementklasse eines ATL-ActiveX-Steuerelements, an die VIEWSTATUS-Flags, die den Container an.

```
DECLARE_VIEW_STATUS( statusFlags )
```

### <a name="parameters"></a>Parameter

*statusFlags*  
[in] Die VIEWSTATUS-Flags. Finden Sie unter [VIEWSTATUS](/windows/desktop/api/ocidl/ne-ocidl-tagviewstatus) für eine Liste von Flags.

### <a name="example"></a>Beispiel

[!code-cpp[NVC_ATL_Windowing#126](../../atl/codesnippet/cpp/aggregation-and-class-factory-macros_9.h)]

## <a name="see-also"></a>Siehe auch

[Makros](../../atl/reference/atl-macros.md)
