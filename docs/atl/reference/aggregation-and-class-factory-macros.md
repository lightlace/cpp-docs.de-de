---
title: Aggregation und Factory-Makros | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- class factories, ATL macros
- aggregation [C++], ATL macros
ms.assetid: d99d379a-0eec-481f-8daa-252dac18f163
caps.latest.revision: 17
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
ms.sourcegitcommit: 604a4bf49490ad2599c857eb3afd527d67e1e25b
ms.openlocfilehash: 4509f7be36e45cf96a938e30ec0f82ec0c9836b5
ms.contentlocale: de-de
ms.lasthandoff: 02/24/2017

---
# <a name="aggregation-and-class-factory-macros"></a>Aggregation und Factory-Makros
Diese Makros ermöglichen das Steuern der Aggregation und Klassenfactorys zu deklarieren.  
  
|||  
|-|-|  
|[DECLARE_AGGREGATABLE](#declare_aggregatable)|Gibt an, dass das Objekt sein kann (Standard) aggregiert.|  
|[DECLARE_CLASSFACTORY](#declare_classfactory)|Deklariert die Klassenfactory sein [CComClassFactory](../../atl/reference/ccomclassfactory-class.md), die ATL-Standard-Klassenfactory.|  
|[DECLARE_CLASSFACTORY_EX](#declare_classfactory_ex)|Deklariert das Klasse Factoryobjekt die Klassenfactory.|  
|[DECLARE_CLASSFACTORY2](#declare_classfactory2)|Deklariert [CComClassFactory2](../../atl/reference/ccomclassfactory2-class.md) die Klassenfactory sein.|  
|[DECLARE_CLASSFACTORY_AUTO_THREAD](#declare_classfactory_auto_thread)|Deklariert [CComClassFactoryAutoThread](../../atl/reference/ccomclassfactoryautothread-class.md) die Klassenfactory sein.|  
|[DECLARE_CLASSFACTORY_SINGLETON](#declare_classfactory_singleton)|Deklariert [CComClassFactorySingleton](../../atl/reference/ccomclassfactorysingleton-class.md) die Klassenfactory sein.|  
|[DECLARE_GET_CONTROLLING_UNKNOWN](#declare_get_controlling_unknown)|Deklariert eine virtuelle `GetControllingUnknown` Funktion.|  
|[DECLARE_NOT_AGGREGATABLE](#declare_not_aggregatable)|Deklariert, dass das Objekt aggregiert werden kann.|  
|[DECLARE_ONLY_AGGREGATABLE](#declare_only_aggregatable)|Deklariert, dass das Objekt aggregiert werden muss.|  
|[DECLARE_POLY_AGGREGATABLE](#declare_poly_aggregatable)|Überprüft den Wert der äußeren unbekannten und deklariert das Objekt aggregiert oder nicht aggregierbar, nach Bedarf.|  
|[DECLARE_PROTECT_FINAL_CONSTRUCT](#declare_protect_final_construct)|Schützt das äußere Objekt löschen, während der Erstellung eines inneren Objekts.|  
|[DECLARE_VIEW_STATUS](#declare_view_status)|Gibt die **VIEWSTATUS** Flags auf den Container.|  

## <a name="requirements"></a>Anforderungen  
 **Header:** Standardschnittstellen  
   
##  <a name="declare_aggregatable"></a>DECLARE_AGGREGATABLE  
 Gibt an, dass das Objekt aggregiert werden kann.  
  
```
DECLARE_AGGREGATABLE( x )
```  
  
### <a name="parameters"></a>Parameter  
 *x*  
 [in] Der Name der Klasse, die Sie als aggregierbar definieren.  
  
### <a name="remarks"></a>Hinweise  
 [CComCoClass](../../atl/reference/ccomcoclass-class.md) enthält dieses Makro, um das Standardmodell für die Aggregation anzugeben. Um diese Standardeinstellung zu überschreiben, geben Sie entweder die [DECLARE_NOT_AGGREGATABLE](#declare_not_aggregatable) oder [DECLARE_ONLY_AGGREGATABLE](#declare_only_aggregatable) Makro in die Klassendefinition.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_ATL_Windowing&#121;](../../atl/codesnippet/cpp/aggregation-and-class-factory-macros_1.h)]  
  
##  <a name="declare_classfactory"></a>DECLARE_CLASSFACTORY  
 Deklariert [CComClassFactory](../../atl/reference/ccomclassfactory-class.md) die Klassenfactory sein.  
  
```
DECLARE_CLASSFACTORY()
```  
  
### <a name="remarks"></a>Hinweise  
 [CComCoClass](../../atl/reference/ccomcoclass-class.md) verwendet dieses Makro, um die Standard-Klassenfactory für Ihr Objekt deklarieren.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_ATL_COM&#55;](../../atl/codesnippet/cpp/aggregation-and-class-factory-macros_2.h)]  
  
##  <a name="ccomclassfactory_class"></a>CComClassFactory-Klasse  
 Diese Klasse implementiert die [IClassFactory](http://msdn.microsoft.com/library/windows/desktop/ms694364) Schnittstelle.  
  
```
class CComClassFactory : public IClassFactory,
public CComObjectRootEx<CComGlobalsThreadModel>
```  
  
### <a name="remarks"></a>Hinweise  
 `CComClassFactory`implementiert die [IClassFactory](http://msdn.microsoft.com/library/windows/desktop/ms694364) -Schnittstelle, die Methoden für das Erstellen eines Objekts einer bestimmten CLSID sowie das Sperren der Klassenfactory im Arbeitsspeicher, um neue Objekte schneller erstellt werden können. **IClassFactory** für jede Klasse, die Sie in der Registrierung und die CLSID zuweisen registrieren implementiert werden muss.  
  
 ATL-Objekte abrufen eine Klassenfactory normalerweise durch Ableiten von [CComCoClass](../../atl/reference/ccomcoclass-class.md). Diese Klasse enthält das Makro [DECLARE_CLASSFACTORY](#declare_classfactory), die deklariert wird, `CComClassFactory` als die standardmäßige Klassenfactory. Um diese Standardeinstellung zu überschreiben, geben Sie einen von der `DECLARE_CLASSFACTORY` *XXX* Makros in die Klassendefinition. Zum Beispiel die [DECLARE_CLASSFACTORY_EX](#declare_classfactory_ex) Makro verwendet die angegebene Klasse für die Klassenfactory:  
  
 [!code-cpp[NVC_ATL_COM&#8;](../../atl/codesnippet/cpp/aggregation-and-class-factory-macros_3.h)]  
  
 Die oben genannten Klassendefinition gibt an, dass **CMyClassFactory** als Standard-Klassenfactory des Objekts verwendet wird. **CMyClassFactory** durch Ableiten von `CComClassFactory` , und überschreiben Sie `CreateInstance`.  
  
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
 [in] Der Name der Klasse, die Ihre Klasse Factory-Objekt implementiert.  
  
### <a name="remarks"></a>Hinweise  
 Die `cf` Parameter Ableiten von [CComClassFactory](../../atl/reference/ccomclassfactory-class.md) und überschreiben die `CreateInstance` Methode.  
  
 [CComCoClass](../../atl/reference/ccomcoclass-class.md) enthält die [DECLARE_CLASSFACTORY](#declare_classfactory) -Makro, das gibt `CComClassFactory` als die standardmäßige Klassenfactory. Allerdings dazu die `DECLARE_CLASSFACTORY_EX` Makro in der Klassendefinition des Objekts, überschreiben Sie diese Standardeinstellung.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_ATL_COM&#8;](../../atl/codesnippet/cpp/aggregation-and-class-factory-macros_3.h)]  
  
##  <a name="declare_classfactory2"></a>DECLARE_CLASSFACTORY2  
 Deklariert [CComClassFactory2](../../atl/reference/ccomclassfactory2-class.md) die Klassenfactory sein.  
  
```
DECLARE_CLASSFACTORY2( lic )
```  
  
### <a name="parameters"></a>Parameter  
 *LIC*  
 [in] Eine Klasse, die implementiert `VerifyLicenseKey`, `GetLicenseKey`, und `IsLicenseValid`.  
  
### <a name="remarks"></a>Hinweise  
 [CComCoClass](../../atl/reference/ccomcoclass-class.md) enthält die [DECLARE_CLASSFACTORY](#declare_classfactory) -Makro, das gibt [CComClassFactory](../../atl/reference/ccomclassfactory-class.md) als die standardmäßige Klassenfactory. Allerdings dazu die `DECLARE_CLASSFACTORY2` Makro in der Klassendefinition des Objekts, überschreiben Sie diese Standardeinstellung.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_ATL_COM&#2;](../../atl/codesnippet/cpp/aggregation-and-class-factory-macros_4.h)]  
  
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
  
- **statische BOOL GetLicenseKey (DWORD** `dwReserved` **, BSTR\* ** `pBstr` **);**  
  
- **statische BOOL IsLicenseValid ();**  
  
### <a name="remarks"></a>Hinweise  
 `CComClassFactory2`implementiert die [IClassFactory2](http://msdn.microsoft.com/library/windows/desktop/ms692720) -Schnittstelle, die eine Erweiterung der [IClassFactory](http://msdn.microsoft.com/library/windows/desktop/ms694364). **IClassFactory2** Steuerelemente-Objekt erstellen, die über eine Lizenz. Eine Klasse Factory ausgeführt auf einem lizenzierten Computer kann zur Laufzeit Lizenzschlüssel bereitstellen. Dieser Lizenzschlüssel kann eine Anwendung Objekte zu instanziieren, wenn eine vollständige Computer Lizenz nicht vorhanden ist.  
  
 ATL-Objekte abrufen eine Klassenfactory normalerweise durch Ableiten von [CComCoClass](../../atl/reference/ccomcoclass-class.md). Diese Klasse enthält das Makro [DECLARE_CLASSFACTORY](#declare_classfactory), die deklariert wird, [CComClassFactory](../../atl/reference/ccomclassfactory-class.md) als die standardmäßige Klassenfactory. Mit `CComClassFactory2`, geben Sie die [DECLARE_CLASSFACTORY2](#declare_classfactory2) Makro in die Definition der Klasse des Objekts. Zum Beispiel:  
  
 [!code-cpp[NVC_ATL_COM&#2;](../../atl/codesnippet/cpp/aggregation-and-class-factory-macros_4.h)]  
  
 **CMyLicense**, der Vorlagenparameter `CComClassFactory2`, müssen die statischen Funktionen implementieren `VerifyLicenseKey`, `GetLicenseKey`, und `IsLicenseValid`. Im folgenden finden ein Beispiel für eine einfache Lizenzklasse:  
  
 [!code-cpp[NVC_ATL_COM&3;](../../atl/codesnippet/cpp/aggregation-and-class-factory-macros_5.h)]  
  
 `CComClassFactory2`Beide abgeleitet **CComClassFactory2Base** und *Lizenz*. **CComClassFactory2Base**, leitet sich wiederum aus **IClassFactory2** und **CComObjectRootEx\< CComGlobalsThreadModel >**.  
  
##  <a name="declare_classfactory_auto_thread"></a>DECLARE_CLASSFACTORY_AUTO_THREAD  
 Deklariert [CComClassFactoryAutoThread](../../atl/reference/ccomclassfactoryautothread-class.md) die Klassenfactory sein.  
  
```
DECLARE_CLASSFACTORY_AUTO_THREAD()
```  
  
### <a name="remarks"></a>Hinweise  
 [CComCoClass](../../atl/reference/ccomcoclass-class.md) enthält die [DECLARE_CLASSFACTORY](#declare_classfactory) -Makro, das gibt [CComClassFactory](../../atl/reference/ccomclassfactory-class.md) als die standardmäßige Klassenfactory. Allerdings dazu die `DECLARE_CLASSFACTORY_AUTO_THREAD` Makro in der Klassendefinition des Objekts, überschreiben Sie diese Standardeinstellung.  
  
 Fügen Sie beim Erstellen von Objekten in mehreren Apartments (in einem Out-of-Proc-Server) `DECLARE_CLASSFACTORY_AUTO_THREAD` zu Ihrer Klasse.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_ATL_COM&#9;](../../atl/codesnippet/cpp/aggregation-and-class-factory-macros_6.h)]  
  
##  <a name="ccomclassfactoryautothread_class"></a>CComClassFactoryAutoThread-Klasse  
 Diese Klasse implementiert die [IClassFactory](http://msdn.microsoft.com/library/windows/desktop/ms694364) Schnittstelle und ermöglicht es Objekten, die in mehreren Apartments erstellt werden.  
  
> [!IMPORTANT]
>  Diese Klasse und ihre Member werden nicht in Anwendungen verwendet, die in der Windows-Runtime ausgeführt.  
  
```
class CComClassFactoryAutoThread : public IClassFactory,
public CComObjectRootEx<CComGlobalsThreadModel>
```  
  
### <a name="remarks"></a>Hinweise  
 `CComClassFactoryAutoThread`ähnelt dem [CComClassFactory](../../atl/reference/ccomclassfactory-class.md), aber ermöglicht es Objekten, die in mehreren Apartments erstellt werden. Um diese Unterstützung nutzen zu können, leiten Sie die EXE-Moduls aus [CComAutoThreadModule](../../atl/reference/ccomautothreadmodule-class.md).  
  
 ATL-Objekte abrufen eine Klassenfactory normalerweise durch Ableiten von [CComCoClass](../../atl/reference/ccomcoclass-class.md). Diese Klasse enthält das Makro [DECLARE_CLASSFACTORY](#declare_classfactory), die deklariert wird, [CComClassFactory](../../atl/reference/ccomclassfactory-class.md) als die standardmäßige Klassenfactory. Mit `CComClassFactoryAutoThread`, geben Sie die [DECLARE_CLASSFACTORY_AUTO_THREAD](#declare_classfactory_auto_thread) Makro in die Definition der Klasse des Objekts. Zum Beispiel:  
  
 [!code-cpp[NVC_ATL_COM&#9;](../../atl/codesnippet/cpp/aggregation-and-class-factory-macros_6.h)]  
  
##  <a name="declare_classfactory_singleton"></a>DECLARE_CLASSFACTORY_SINGLETON  
 Deklariert [CComClassFactorySingleton](../../atl/reference/ccomclassfactorysingleton-class.md) die Klassenfactory sein.  
  
```
DECLARE_CLASSFACTORY_SINGLETON( obj )
```  
  
### <a name="parameters"></a>Parameter  
 `obj`  
 [in] Der Name der Class-Objekt.  
  
### <a name="remarks"></a>Hinweise  
 [CComCoClass](../../atl/reference/ccomcoclass-class.md) enthält die [DECLARE_CLASSFACTORY](#declare_classfactory) -Makro, das gibt [CComClassFactory](../../atl/reference/ccomclassfactory-class.md) als die standardmäßige Klassenfactory. Allerdings dazu die `DECLARE_CLASSFACTORY_SINGLETON` Makro in der Klassendefinition des Objekts, überschreiben Sie diese Standardeinstellung.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_ATL_COM&#10;](../../atl/codesnippet/cpp/aggregation-and-class-factory-macros_7.h)]  
  
##  <a name="ccomclassfactorysingleton_class"></a>CComClassFactorySingleton-Klasse  
 Diese Klasse wird von [CComClassFactory](../../atl/reference/ccomclassfactory-class.md) und [CComObjectGlobal](../../atl/reference/ccomobjectglobal-class.md) ein einzelnes Objekt zu erstellen.  
  
> [!IMPORTANT]
>  Diese Klasse und ihre Member werden nicht in Anwendungen verwendet, die in der Windows-Runtime ausgeführt.  
  
```
template<class T>
class CComClassFactorySingleton : public CComClassFactory
```  
  
### <a name="parameters"></a>Parameter  
 `T`  
 Die Klasse.  
  
 `CComClassFactorySingleton`leitet sich von [CComClassFactory](../../atl/reference/ccomclassfactory-class.md) und [CComObjectGlobal](../../atl/reference/ccomobjectglobal-class.md) ein einzelnes Objekt zu erstellen. Jeder Aufruf von der `CreateInstance` -Methode fragt einfach dieses Objekts für einen Schnittstellenzeiger auf.  
  
### <a name="remarks"></a>Hinweise  
 ATL-Objekte abrufen eine Klassenfactory normalerweise durch Ableiten von [CComCoClass](../../atl/reference/ccomcoclass-class.md). Diese Klasse enthält das Makro [DECLARE_CLASSFACTORY](#declare_classfactory), die deklariert wird, `CComClassFactory` als die standardmäßige Klassenfactory. Mit `CComClassFactorySingleton`, geben Sie die [DECLARE_CLASSFACTORY_SINGLETON](#declare_classfactory_singleton) Makro in die Definition der Klasse des Objekts. Zum Beispiel:  
  
 [!code-cpp[NVC_ATL_COM&#10;](../../atl/codesnippet/cpp/aggregation-and-class-factory-macros_7.h)]  
  
##  <a name="declare_get_controlling_unknown"></a>DECLARE_GET_CONTROLLING_UNKNOWN  
 Deklariert eine virtuelle Funktion `GetControllingUnknown`.  
  
```
DECLARE_GET_CONTROLLING_UNKNOWN()
```  
  
### <a name="remarks"></a>Hinweise  
 Dieses Makro für Ihr Objekt hinzufügen, wenn Sie die Fehlermeldung des Compilers erhalten `GetControllingUnknown` ist nicht definiert (z. B. in **CComAggregateCreator**).  
  
##  <a name="declare_not_aggregatable"></a>DECLARE_NOT_AGGREGATABLE  
 Gibt an, dass das Objekt aggregiert werden kann.  
  
```
DECLARE_NOT_AGGREGATABLE( x )
```  
  
### <a name="parameters"></a>Parameter  
 *x*  
 [in] Der Name des Klassenobjekts, die Sie als nicht aggregierbar definieren.  
  
### <a name="remarks"></a>Hinweise  
 `DECLARE_NOT_AGGREGATABLE`bewirkt, dass `CreateInstance` einen Fehler zurückgegeben ( **CLASS_E_NOAGGREGATION**), wenn versucht wird für die Aggregation auf das Objekt.  
  
 In der Standardeinstellung [CComCoClass](../../atl/reference/ccomcoclass-class.md) enthält die [DECLARE_AGGREGATABLE](#declare_aggregatable) -Makro, das angibt, dass das Objekt aggregiert werden kann. Um dieses Standardverhalten zu überschreiben, gehören `DECLARE_NOT_AGGREGATABLE` in die Klassendefinition.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_ATL_Windowing&#121;](../../atl/codesnippet/cpp/aggregation-and-class-factory-macros_1.h)]  
  
##  <a name="declare_only_aggregatable"></a>DECLARE_ONLY_AGGREGATABLE  
 Gibt an, dass das Objekt aggregiert werden muss.  
  
```
DECLARE_ONLY_AGGREGATABLE( x )
```  
  
### <a name="parameters"></a>Parameter  
 *x*  
 [in] Der Name des Klassenobjekts, die Sie als nur aggregierbar definieren.  
  
### <a name="remarks"></a>Hinweise  
 `DECLARE_ONLY_AGGREGATABLE`verursacht einen Fehler ( **E_FAIL**), wenn ein Versuch **CoCreate** das Objekt als nicht zusammengesetztes Objekt.  
  
 In der Standardeinstellung [CComCoClass](../../atl/reference/ccomcoclass-class.md) enthält die [DECLARE_AGGREGATABLE](#declare_aggregatable) -Makro, das angibt, dass das Objekt aggregiert werden kann. Um dieses Standardverhalten zu überschreiben, gehören `DECLARE_ONLY_AGGREGATABLE` in die Klassendefinition.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_ATL_Windowing&#125;](../../atl/codesnippet/cpp/aggregation-and-class-factory-macros_8.h)]  
  
##  <a name="declare_poly_aggregatable"></a>DECLARE_POLY_AGGREGATABLE  
 Gibt an, dass eine Instanz von **CComPolyObject \< ** *x* ** > ** wird erstellt, wenn das Objekt erstellt wird.  
  
```
DECLARE_POLY_AGGREGATABLE( x )
```  
  
### <a name="parameters"></a>Parameter  
 *x*  
 [in] Der Name des Klassenobjekts, die Sie als aggregierbaren oder nicht aggregierbar definieren.  
  
### <a name="remarks"></a>Hinweise  
 Während der Erstellung wird der Wert der äußeren unbekannten überprüft. Ist dies **NULL**, **IUnknown** ist für ein nicht zusammengesetztes Objekt implementiert. Wenn die äußere unbekannte nicht **NULL**, **IUnknown** für ein zusammengesetztes Objekt implementiert wird.  
  
 Der Vorteil der Verwendung `DECLARE_POLY_AGGREGATABLE` besteht darin, dass Sie vermeiden, dass beide `CComAggObject` und `CComObject` in Ihrem Modul zusammengefasste und aggregierte behandelt. Ein einzelnes `CComPolyObject` -Objekt verarbeitet beide Fälle. Dies bedeutet, dass nur eine Kopie der Vtable und eine Kopie der Funktionen im Modul vorhanden sind. Wenn die Vtable umfangreich ist, kann dies Modulgröße erheblich beeinträchtigen. Wenn die Vtable klein ist, jedoch mithilfe `CComPolyObject` kann in einem etwas größeren Modul führen, da er nicht für ein Objekt aggregierten oder aggregierte optimiert ist wie `CComAggObject` und `CComObject`.  
  
 Die `DECLARE_POLY_AGGREGATABLE` Makro wird automatisch in das Objekt deklariert, wenn Sie den ATL-Steuerelement-Assistenten verwenden, erstellen Sie eine vollständige Kontrolle.  
  
##  <a name="declare_protect_final_construct"></a>DECLARE_PROTECT_FINAL_CONSTRUCT  

 Verhindert, dass das Objekt gelöscht wird, wenn (während der [FinalConstruct](ccomobjectrootex-class.md#finalconstruct)) der internen zusammengesetzten Objekts den Verweiszähler und verringert erhöht die Anzahl auf 0.  
  
```
DECLARE_PROTECT_FINAL_CONSTRUCT()
```  
  
##  <a name="declare_view_status"></a>DECLARE_VIEW_STATUS  
 Setzen Sie dieses Makro in ein ATL-ActiveX-Steuerelement-Steuerelementklasse an die **VIEWSTATUS** Flags auf den Container.  
  
```
DECLARE_VIEW_STATUS( statusFlags )
```  
  
### <a name="parameters"></a>Parameter  
 `statusFlags`  
 [in] Die **VIEWSTATUS** Flags. Finden Sie unter [VIEWSTATUS](http://msdn.microsoft.com/library/windows/desktop/ms687201) für eine Liste mit Flags.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_ATL_Windowing&#126;](../../atl/codesnippet/cpp/aggregation-and-class-factory-macros_9.h)]  
  
## <a name="see-also"></a>Siehe auch  
 [Makros](../../atl/reference/atl-macros.md)

