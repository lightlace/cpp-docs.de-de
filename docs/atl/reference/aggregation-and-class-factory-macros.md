---
title: Aggregation und Klasse Factory Makros | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
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
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 8d18afdfe08a97a7a685b373b1f8951799836ab1
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="aggregation-and-class-factory-macros"></a>Aggregation und Klasse Factory-Makros
Diese Makros können steuern, Aggregation und Klassenfactorys deklarieren.  
  
|||  
|-|-|  
|[DECLARE_AGGREGATABLE](#declare_aggregatable)|Deklariert, dass Ihr Objekt verwendet werden (Standardeinstellung) aggregiert.|  
|[DECLARE_CLASSFACTORY](#declare_classfactory)|Deklariert die Klassenfactory sein [CComClassFactory](../../atl/reference/ccomclassfactory-class.md), die ATL-standardfactory-Klasse.|  
|[DECLARE_CLASSFACTORY_EX](#declare_classfactory_ex)|Deklariert Ihrer Factory-Klassenobjekt die Klassenfactory sein.|  
|[DECLARE_CLASSFACTORY2](#declare_classfactory2)|Deklariert [CComClassFactory2](../../atl/reference/ccomclassfactory2-class.md) die Klassenfactory sein.|  
|[DECLARE_CLASSFACTORY_AUTO_THREAD](#declare_classfactory_auto_thread)|Deklariert [CComClassFactoryAutoThread](../../atl/reference/ccomclassfactoryautothread-class.md) die Klassenfactory sein.|  
|[DECLARE_CLASSFACTORY_SINGLETON](#declare_classfactory_singleton)|Deklariert [CComClassFactorySingleton](../../atl/reference/ccomclassfactorysingleton-class.md) die Klassenfactory sein.|  
|[DECLARE_GET_CONTROLLING_UNKNOWN](#declare_get_controlling_unknown)|Deklariert eine virtuelle `GetControllingUnknown` Funktion.|  
|[DECLARE_NOT_AGGREGATABLE](#declare_not_aggregatable)|Deklariert, dass das Objekt nicht aggregiert werden kann.|  
|[DECLARE_ONLY_AGGREGATABLE](#declare_only_aggregatable)|Deklariert, dass das Objekt aggregiert werden muss.|  
|[DECLARE_POLY_AGGREGATABLE](#declare_poly_aggregatable)|Überprüft den Wert, der die äußere unbekannte und Ihr Objekt deklariert, aggregierbar oder nicht aggregierbar, je nach Bedarf.|  
|[DECLARE_PROTECT_FINAL_CONSTRUCT](#declare_protect_final_construct)|Schützt das äußere Objekt löschen, während der Erstellung eines inneren Objekts.|  
|[DECLARE_VIEW_STATUS](#declare_view_status)|Gibt an, die **VIEWSTATUS** Flags für den Container.|  

## <a name="requirements"></a>Anforderungen  
 **Header:** atlcom.h  
   
##  <a name="declare_aggregatable"></a>DECLARE_AGGREGATABLE  
 Gibt an, dass das Objekt aggregiert werden kann.  
  
```
DECLARE_AGGREGATABLE( x )
```  
  
### <a name="parameters"></a>Parameter  
 *w*  
 [in] Der Name der Klasse, die Sie als aggregierbar definieren.  
  
### <a name="remarks"></a>Hinweise  
 [CComCoClass](../../atl/reference/ccomcoclass-class.md) enthält dieses Makro, um das Standardmodell für die Aggregation anzugeben. Um diese Standardeinstellung zu überschreiben, geben Sie entweder die [DECLARE_NOT_AGGREGATABLE](#declare_not_aggregatable) oder [DECLARE_ONLY_AGGREGATABLE](#declare_only_aggregatable) Makros in der Klasse.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_ATL_Windowing#121](../../atl/codesnippet/cpp/aggregation-and-class-factory-macros_1.h)]  
  
##  <a name="declare_classfactory"></a>DECLARE_CLASSFACTORY  
 Deklariert [CComClassFactory](../../atl/reference/ccomclassfactory-class.md) die Klassenfactory sein.  
  
```
DECLARE_CLASSFACTORY()
```  
  
### <a name="remarks"></a>Hinweise  
 [CComCoClass](../../atl/reference/ccomcoclass-class.md) dieses Makro zum Deklarieren der Klasse standardfactory für Ihr Objekt verwendet.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_ATL_COM#55](../../atl/codesnippet/cpp/aggregation-and-class-factory-macros_2.h)]  
  
##  <a name="ccomclassfactory_class"></a>CComClassFactory-Klasse  
 Diese Klasse implementiert die [IClassFactory](http://msdn.microsoft.com/library/windows/desktop/ms694364) Schnittstelle.  
  
```
class CComClassFactory : public IClassFactory,
public CComObjectRootEx<CComGlobalsThreadModel>
```  
  
### <a name="remarks"></a>Hinweise  
 `CComClassFactory`implementiert die [IClassFactory](http://msdn.microsoft.com/library/windows/desktop/ms694364) -Schnittstelle, die enthält Methoden zum Erstellen eines Objekts von einem bestimmten CLSID sowie das Sperren der Klassenfactory im Arbeitsspeicher, damit neue Objekte schneller erstellt werden können. **IClassFactory** muss für jede Klasse, die Sie in der Registrierung und Zuweisen von dem Sie CLSID registrieren implementiert werden.  
  
 ATL-Objekte abrufen eine Klassenfactory normalerweise durch Ableiten von [CComCoClass](../../atl/reference/ccomcoclass-class.md). Diese Klasse enthält das Makro [DECLARE_CLASSFACTORY](#declare_classfactory), die deklariert wird, `CComClassFactory` als der standardfactory-Klasse. Um diese Standardeinstellung zu überschreiben, geben Sie einen von der `DECLARE_CLASSFACTORY` *XXX* Makros in der Klasse. Z. B. die [DECLARE_CLASSFACTORY_EX](#declare_classfactory_ex) Makro verwendet die angegebene Klasse für die Klassenfactory:  
  
 [!code-cpp[NVC_ATL_COM#8](../../atl/codesnippet/cpp/aggregation-and-class-factory-macros_3.h)]  
  
 Die oben genannten Klassendefinition gibt an, dass **CMyClassFactory** als Klassenfactory für das Objekt standardmäßig verwendet wird. **CMyClassFactory** leiten von `CComClassFactory` und überschreiben `CreateInstance`.  
  
 ATL stellt drei Makros, die eine Klassenfactory deklarieren:  
  
- [DECLARE_CLASSFACTORY2](#declare_classfactory2) verwendet [CComClassFactory2](../../atl/reference/ccomclassfactory2-class.md), welche Steuerelemente erstellen, die über eine Lizenz.  
  
- [DECLARE_CLASSFACTORY_AUTO_THREAD](#declare_classfactory_auto_thread) verwendet [CComClassFactoryAutoThread](../../atl/reference/ccomclassfactoryautothread-class.md), die Objekte in mehreren Apartments erstellt.  
  
- [DECLARE_CLASSFACTORY_SINGLETON](#declare_classfactory_singleton) verwendet [CComClassFactorySingleton](../../atl/reference/ccomclassfactorysingleton-class.md), die ein einzelnes erstellt [CComObjectGlobal](../../atl/reference/ccomobjectglobal-class.md) Objekt.  
  
##  <a name="declare_classfactory_ex"></a>DECLARE_CLASSFACTORY_EX  
 Deklariert `cf` die Klassenfactory sein.  
  
```
DECLARE_CLASSFACTORY_EX( cf )
```  
  
### <a name="parameters"></a>Parameter  
 `cf`  
 [in] Der Name der Klasse, die Ihre Klassenfactoryobjekt implementiert.  
  
### <a name="remarks"></a>Hinweise  
 Die `cf` Parameter ableiten muss [CComClassFactory](../../atl/reference/ccomclassfactory-class.md) und überschreiben die `CreateInstance` Methode.  
  
 [CComCoClass](../../atl/reference/ccomcoclass-class.md) enthält die [DECLARE_CLASSFACTORY](#declare_classfactory) -Makro, das gibt `CComClassFactory` als Standard-Klassenfactory. Allerdings dazu die `DECLARE_CLASSFACTORY_EX` Makro in Klassendefinition des Objekts, überschreiben Sie diese Standardeinstellung.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_ATL_COM#8](../../atl/codesnippet/cpp/aggregation-and-class-factory-macros_3.h)]  
  
##  <a name="declare_classfactory2"></a>DECLARE_CLASSFACTORY2  
 Deklariert [CComClassFactory2](../../atl/reference/ccomclassfactory2-class.md) die Klassenfactory sein.  
  
```
DECLARE_CLASSFACTORY2( lic )
```  
  
### <a name="parameters"></a>Parameter  
 *– lizenzveREINBARUNG*  
 [in] Eine Klasse, die implementiert `VerifyLicenseKey`, `GetLicenseKey`, und `IsLicenseValid`.  
  
### <a name="remarks"></a>Hinweise  
 [CComCoClass](../../atl/reference/ccomcoclass-class.md) enthält die [DECLARE_CLASSFACTORY](#declare_classfactory) -Makro, das gibt [CComClassFactory](../../atl/reference/ccomclassfactory-class.md) als Standard-Klassenfactory. Allerdings dazu die `DECLARE_CLASSFACTORY2` Makro in Klassendefinition des Objekts, überschreiben Sie diese Standardeinstellung.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_ATL_COM#2](../../atl/codesnippet/cpp/aggregation-and-class-factory-macros_4.h)]  
  
##  <a name="ccomclassfactory2_class"></a>CComClassFactory2-Klasse  
 Diese Klasse implementiert die [IClassFactory2](http://msdn.microsoft.com/library/windows/desktop/ms692720) Schnittstelle.  
  
```
template <class license>
class  CComClassFactory2 : public IClassFactory2,
    public CComObjectRootEx<CComGlobalsThreadModel>,
    public license
```    
  
### <a name="parameters"></a>Parameter  
 *Lizenz*  
 Eine Klasse, die folgenden statischen Funktionen implementiert:  
  
- **statische BOOL VerifyLicenseKey (BSTR** `bstr` **);**  
  
- **statische BOOL GetLicenseKey (DWORD** `dwReserved` **, BSTR\***  `pBstr` **);**  
  
- **statische IsLicenseValid BOOL ();**  
  
### <a name="remarks"></a>Hinweise  
 `CComClassFactory2`implementiert die [IClassFactory2](http://msdn.microsoft.com/library/windows/desktop/ms692720) -Schnittstelle, die eine Erweiterung der [IClassFactory](http://msdn.microsoft.com/library/windows/desktop/ms694364). **IClassFactory2** Steuerelemente Objekt erstellen, die über eine Lizenz. Eine Klasse Factory ausführen auf eine lizenzierte Computer kann einen Laufzeit-Lizenzschlüssel bereitstellen. Diese Lizenzschlüssel ermöglicht eine Anwendung, um Objekte zu instanziieren, wenn eine Lizenz für die vollständige Computer nicht vorhanden ist.  
  
 ATL-Objekte abrufen eine Klassenfactory normalerweise durch Ableiten von [CComCoClass](../../atl/reference/ccomcoclass-class.md). Diese Klasse enthält das Makro [DECLARE_CLASSFACTORY](#declare_classfactory), die deklariert wird, [CComClassFactory](../../atl/reference/ccomclassfactory-class.md) als der standardfactory-Klasse. Mit `CComClassFactory2`, geben Sie die [DECLARE_CLASSFACTORY2](#declare_classfactory2) Makro in die Definition der Klasse des Objekts. Zum Beispiel:  
  
 [!code-cpp[NVC_ATL_COM#2](../../atl/codesnippet/cpp/aggregation-and-class-factory-macros_4.h)]  
  
 **CMyLicense**, der Vorlagenparameter `CComClassFactory2`, muss die statischen Funktionen implementieren `VerifyLicenseKey`, `GetLicenseKey`, und `IsLicenseValid`. Im folgenden finden ein Beispiel einer einfachen Lizenz-Klasse:  
  
 [!code-cpp[NVC_ATL_COM#3](../../atl/codesnippet/cpp/aggregation-and-class-factory-macros_5.h)]  
  
 `CComClassFactory2`leitet sich von sowohl **CComClassFactory2Base** und *Lizenz*. **CComClassFactory2Base**, leitet sich wiederum von **IClassFactory2** und **CComObjectRootEx\< CComGlobalsThreadModel >**.  
  
##  <a name="declare_classfactory_auto_thread"></a>DECLARE_CLASSFACTORY_AUTO_THREAD  
 Deklariert [CComClassFactoryAutoThread](../../atl/reference/ccomclassfactoryautothread-class.md) die Klassenfactory sein.  
  
```
DECLARE_CLASSFACTORY_AUTO_THREAD()
```  
  
### <a name="remarks"></a>Hinweise  
 [CComCoClass](../../atl/reference/ccomcoclass-class.md) enthält die [DECLARE_CLASSFACTORY](#declare_classfactory) -Makro, das gibt [CComClassFactory](../../atl/reference/ccomclassfactory-class.md) als Standard-Klassenfactory. Allerdings dazu die `DECLARE_CLASSFACTORY_AUTO_THREAD` Makro in Klassendefinition des Objekts, überschreiben Sie diese Standardeinstellung.  
  
 Beim Erstellen von Objekten in mehreren Apartments (in einem Out-of-Proc-Server) hinzufügen `DECLARE_CLASSFACTORY_AUTO_THREAD` zur-Klasse.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_ATL_COM#9](../../atl/codesnippet/cpp/aggregation-and-class-factory-macros_6.h)]  
  
##  <a name="ccomclassfactoryautothread_class"></a>CComClassFactoryAutoThread-Klasse  
 Diese Klasse implementiert die [IClassFactory](http://msdn.microsoft.com/library/windows/desktop/ms694364) Schnittstelle, und ermöglicht es Objekten, die in mehreren Apartments erstellt werden.  
  
> [!IMPORTANT]
>  Diese Klasse und ihre Member können nicht in Anwendungen verwendet werden, die in der Windows-Runtime ausgeführt.  
  
```
class CComClassFactoryAutoThread : public IClassFactory,
public CComObjectRootEx<CComGlobalsThreadModel>
```  
  
### <a name="remarks"></a>Hinweise  
 `CComClassFactoryAutoThread`ähnelt dem [CComClassFactory](../../atl/reference/ccomclassfactory-class.md), aber ermöglicht es Objekten, die in mehreren Apartments erstellt werden. Dieser Unterstützung profitieren zu können, leiten Sie die EXE-Moduls aus [CComAutoThreadModule](../../atl/reference/ccomautothreadmodule-class.md).  
  
 ATL-Objekte abrufen eine Klassenfactory normalerweise durch Ableiten von [CComCoClass](../../atl/reference/ccomcoclass-class.md). Diese Klasse enthält das Makro [DECLARE_CLASSFACTORY](#declare_classfactory), die deklariert wird, [CComClassFactory](../../atl/reference/ccomclassfactory-class.md) als der standardfactory-Klasse. Mit `CComClassFactoryAutoThread`, geben Sie die [DECLARE_CLASSFACTORY_AUTO_THREAD](#declare_classfactory_auto_thread) Makro in die Definition der Klasse des Objekts. Zum Beispiel:  
  
 [!code-cpp[NVC_ATL_COM#9](../../atl/codesnippet/cpp/aggregation-and-class-factory-macros_6.h)]  
  
##  <a name="declare_classfactory_singleton"></a>DECLARE_CLASSFACTORY_SINGLETON  
 Deklariert [CComClassFactorySingleton](../../atl/reference/ccomclassfactorysingleton-class.md) die Klassenfactory sein.  
  
```
DECLARE_CLASSFACTORY_SINGLETON( obj )
```  
  
### <a name="parameters"></a>Parameter  
 `obj`  
 [in] Der Name des Klassenobjekts.  
  
### <a name="remarks"></a>Hinweise  
 [CComCoClass](../../atl/reference/ccomcoclass-class.md) enthält die [DECLARE_CLASSFACTORY](#declare_classfactory) -Makro, das gibt [CComClassFactory](../../atl/reference/ccomclassfactory-class.md) als Standard-Klassenfactory. Allerdings dazu die `DECLARE_CLASSFACTORY_SINGLETON` Makro in Klassendefinition des Objekts, überschreiben Sie diese Standardeinstellung.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_ATL_COM#10](../../atl/codesnippet/cpp/aggregation-and-class-factory-macros_7.h)]  
  
##  <a name="ccomclassfactorysingleton_class"></a>CComClassFactorySingleton-Klasse  
 Diese Klasse leitet sich von [CComClassFactory](../../atl/reference/ccomclassfactory-class.md) und verwendet [CComObjectGlobal](../../atl/reference/ccomobjectglobal-class.md) So erstellen Sie ein einzelnes Objekt.  
  
> [!IMPORTANT]
>  Diese Klasse und ihre Member können nicht in Anwendungen verwendet werden, die in der Windows-Runtime ausgeführt.  
  
```
template<class T>
class CComClassFactorySingleton : public CComClassFactory
```  
  
### <a name="parameters"></a>Parameter  
 `T`  
 Die Klasse.  
  
 `CComClassFactorySingleton`leitet sich von [CComClassFactory](../../atl/reference/ccomclassfactory-class.md) und verwendet [CComObjectGlobal](../../atl/reference/ccomobjectglobal-class.md) So erstellen Sie ein einzelnes Objekt. Bei jedem Aufruf der `CreateInstance` Methode fragt einfach dieses Objekts für einen Schnittstellenzeiger auf.  
  
### <a name="remarks"></a>Hinweise  
 ATL-Objekte abrufen eine Klassenfactory normalerweise durch Ableiten von [CComCoClass](../../atl/reference/ccomcoclass-class.md). Diese Klasse enthält das Makro [DECLARE_CLASSFACTORY](#declare_classfactory), die deklariert wird, `CComClassFactory` als der standardfactory-Klasse. Mit `CComClassFactorySingleton`, geben Sie die [DECLARE_CLASSFACTORY_SINGLETON](#declare_classfactory_singleton) Makro in die Definition der Klasse des Objekts. Zum Beispiel:  
  
 [!code-cpp[NVC_ATL_COM#10](../../atl/codesnippet/cpp/aggregation-and-class-factory-macros_7.h)]  
  
##  <a name="declare_get_controlling_unknown"></a>DECLARE_GET_CONTROLLING_UNKNOWN  
 Deklariert eine virtuelle Funktion `GetControllingUnknown`.  
  
```
DECLARE_GET_CONTROLLING_UNKNOWN()
```  
  
### <a name="remarks"></a>Hinweise  
 Dieses Makro für Ihr Objekt hinzufügen, wenn Sie die Fehlermeldung des Compilers erhalten `GetControllingUnknown` ist nicht definiert (z. B. in **CComAggregateCreator**).  
  
##  <a name="declare_not_aggregatable"></a>DECLARE_NOT_AGGREGATABLE  
 Gibt an, dass das Objekt kann nicht aggregiert werden.  
  
```
DECLARE_NOT_AGGREGATABLE( x )
```  
  
### <a name="parameters"></a>Parameter  
 *w*  
 [in] Der Name des Klassenobjekts werden Sie als nicht aggregierbar definieren.  
  
### <a name="remarks"></a>Hinweise  
 `DECLARE_NOT_AGGREGATABLE`bewirkt, dass `CreateInstance` einen Fehler zurückgegeben ( **CLASS_E_NOAGGREGATION**) wird ein Versuch unternommen an, die auf das Objekt aggregiert.  
  
 Standardmäßig [CComCoClass](../../atl/reference/ccomcoclass-class.md) enthält die [DECLARE_AGGREGATABLE](#declare_aggregatable) -Makro, das gibt an, dass das Objekt aggregiert werden kann. Um dieses Standardverhalten zu überschreiben, umfassen `DECLARE_NOT_AGGREGATABLE` in der Klasse.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_ATL_Windowing#121](../../atl/codesnippet/cpp/aggregation-and-class-factory-macros_1.h)]  
  
##  <a name="declare_only_aggregatable"></a>DECLARE_ONLY_AGGREGATABLE  
 Gibt an, dass das Objekt aggregiert werden muss.  
  
```
DECLARE_ONLY_AGGREGATABLE( x )
```  
  
### <a name="parameters"></a>Parameter  
 *w*  
 [in] Der Name des Klassenobjekts werden Sie als nur aggregierbar definieren.  
  
### <a name="remarks"></a>Hinweise  
 `DECLARE_ONLY_AGGREGATABLE`verursacht einen Fehler ( **E_FAIL**), wird ein Versuch unternommen **CoCreate** Ihres Objekts als aggregierte-Objekt.  
  
 Standardmäßig [CComCoClass](../../atl/reference/ccomcoclass-class.md) enthält die [DECLARE_AGGREGATABLE](#declare_aggregatable) -Makro, das gibt an, dass das Objekt aggregiert werden kann. Um dieses Standardverhalten zu überschreiben, umfassen `DECLARE_ONLY_AGGREGATABLE` in der Klasse.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_ATL_Windowing#125](../../atl/codesnippet/cpp/aggregation-and-class-factory-macros_8.h)]  
  
##  <a name="declare_poly_aggregatable"></a>DECLARE_POLY_AGGREGATABLE  
 Gibt an, dass eine Instanz von **CComPolyObject \<**  *x*  **>**  wird erstellt, wenn Ihr Objekt erstellt wird.  
  
```
DECLARE_POLY_AGGREGATABLE( x )
```  
  
### <a name="parameters"></a>Parameter  
 *w*  
 [in] Der Name des Klassenobjekts werden Sie als aggregierbar oder nicht aggregierbar definieren.  
  
### <a name="remarks"></a>Hinweise  
 Während der Erstellung wird der Wert, der die äußere unbekannte überprüft. Ist er **NULL**, **IUnknown** für eine aggregierte Objekt implementiert wird. Wenn die äußere unbekannte nicht **NULL**, **IUnknown** für ein zusammengesetztes Objekt implementiert wird.  
  
 Der Vorteil der Verwendung `DECLARE_POLY_AGGREGATABLE` ist, dass Sie vermeiden, dass beide `CComAggObject` und `CComObject` innerhalb des Moduls, die zusammengefasste und aggregierte Fälle zu behandeln. Ein einzelnes `CComPolyObject` Objekt verarbeitet die beiden Fällen. Dies bedeutet, dass nur eine Kopie der Vtable und eine Kopie der Funktionen, die innerhalb des Moduls vorhanden sind. Wenn Ihre Vtable groß ist, kann dies die Modulgröße erheblich verringern. Jedoch verwenden, wenn die Vtable klein ist, `CComPolyObject` kann dazu führen, etwas Modul größer, da sie nicht für ein Objekt aggregierten oder aggregierte optimiert ist wie `CComAggObject` und `CComObject`.  
  
 Die `DECLARE_POLY_AGGREGATABLE` Makro wird bei Verwendung von ATL-Steuerelement-Assistent zum Erstellen eines vollständigen Steuerelements automatisch in Ihr Objekt deklariert.  
  
##  <a name="declare_protect_final_construct"></a>DECLARE_PROTECT_FINAL_CONSTRUCT  

 Verhindert, dass das Objekt gelöscht werden, wenn (während der [FinalConstruct](ccomobjectrootex-class.md#finalconstruct)) das interne aggregierte Objekt den Verweiszähler dieser Planergruppe und dekrementiert inkrementiert den Verweiszähler auf 0.  
  
```
DECLARE_PROTECT_FINAL_CONSTRUCT()
```  
  
##  <a name="declare_view_status"></a>DECLARE_VIEW_STATUS  
 Platzieren Sie dieses Makro in eine ATL-ActiveX-Steuerelement-Steuerelementklasse an die **VIEWSTATUS** Flags für den Container.  
  
```
DECLARE_VIEW_STATUS( statusFlags )
```  
  
### <a name="parameters"></a>Parameter  
 `statusFlags`  
 [in] Die **VIEWSTATUS** Flags. Finden Sie unter [VIEWSTATUS](http://msdn.microsoft.com/library/windows/desktop/ms687201) für eine Liste von Flags.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_ATL_Windowing#126](../../atl/codesnippet/cpp/aggregation-and-class-factory-macros_9.h)]  
  
## <a name="see-also"></a>Siehe auch  
 [Makros](../../atl/reference/atl-macros.md)
