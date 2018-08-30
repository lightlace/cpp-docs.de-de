---
title: ATL-Klassen und Strukturen | Microsoft-Dokumentation
ms.custom: ''
ms.date: 05/03/2018
ms.technology:
- cpp-atl
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- classes [C++], ATL
- ATL, classes
ms.assetid: 7da42e2d-ac84-4506-92bd-502a86d68bdc
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 71025785fbc9eab2b962e0f9e48ba9170edf1de1
ms.sourcegitcommit: 9a0905c03a73c904014ec9fd3d6e59e4fa7813cd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/29/2018
ms.locfileid: "43204189"
---
# <a name="atl-classes-and-structs"></a>ATL-Klassen und Strukturen
Die Active Template Library (ATL) umfasst die folgenden Klassen und Strukturen. Um eine bestimmte Klasse nach Kategorien suchen zu können, finden Sie unter den [ATL-Klassenübersicht](../../atl/atl-class-overview.md).  
  
|Klasse / Struktur|Beschreibung|Headerdatei|  
|-----------|-----------------|-----------------|  
|[ATL_DRAWINFO](../../atl/reference/atl-drawinfo-structure.md)|Enthält Informationen, die für das Rendering an verschiedene Ziele, z. B. einen Drucker, Metadatei oder ActiveX-Steuerelement verwendet.|atlctl.h|
|[_AtlCreateWndData](../../atl/reference/atlcreatewnddata-structure.md)|Enthält Daten von Klasseninstanzen Windowing-Code in ATL|Atlbase.h|
|[_ATL_BASE_MODULE70](../../atl/reference/atl-base-module70-structure.md)|Ein, die Projekte, die ATL verwendet.|Atlbase.h|  
|[_ATL_COM_MODULE70](../../atl/reference/atl-com-module70-structure.md)|Ein, die COM-bezogenem Code in ATL| Atlbase.h|  
|[_ATL_FUNC_INFO](../../atl/reference/atl-func-info-structure.md)|Enthält Informationen verwendet, um eine Methode oder Eigenschaft auf einen Disp-Schnittstelle zu beschreiben.|Atlcom.h|  
|[_ATL_MODULE70](../../atl/reference/atl-module70-structure.md)|Enthält Daten, die von jedem ATL-Modul verwendet.|Atlbase.h|  
|[_ATL_WIN_MODULE70](../../atl/reference/atl-win-module70-structure.md)|Windowing-Code in ATL verwendet|Atlbase.h|  
|[CA2AEX](../../atl/reference/ca2aex-class.md)|Diese Klasse wird von der Zeichenfolgen-konvertierungsmakros CA2TEX und CT2AEX und der Typedef CA2A verwendet.|atlconv.h|  
|[CA2CAEX](../../atl/reference/ca2caex-class.md)|Diese Klasse wird von Zeichenfolgen-konvertierungsmakros CA2CTEX und CT2CAEX und der Typedef CA2CA verwendet.|atlconv.h|  
|[CA2WEX](../../atl/reference/ca2wex-class.md)|Diese Klasse wird von der Zeichenfolgen-konvertierungsmakros CA2TEX, CA2CTEX, CT2WEX, CT2CWEX wird und der Typedef CA2W verwendet.|atlconv.h|  
|[CAccessToken](../../atl/reference/caccesstoken-class.md)|Diese Klasse ist ein Wrapper für ein Zugriffstoken an.|ATLSecurity.h|  
|[CAcl](../../atl/reference/cacl-class.md)|Diese Klasse ist ein Wrapper für eine Zugriffssteuerungsliste (Access Control List)-Struktur.|ATLSecurity.h|  
|[CAdapt](../../atl/reference/cadapt-class.md)|Diese Vorlage dient dazu, Klassen zu umschließen, die den Adressoperator so umdefinieren, dass eine andere als die Adresse des Objekts zurückgegeben wird.|"atlcomcli.h"|  
|[CAtlArray](../../atl/reference/catlarray-class.md)|Diese Klasse implementiert eine Array-Objekt.|atlcoll.h|  
|[CAtlAutoThreadModule](../../atl/reference/catlautothreadmodule-class.md)|Diese Klasse implementiert einen COM-Server in einem Thread-Pool, Apartment-Modell.|Atlbase.h|  
|[CAtlAutoThreadModuleT](../../atl/reference/catlautothreadmodulet-class.md)|Diese Klasse stellt Methoden zum Implementieren eines COM-Servers in einem Thread-Pool, Apartment-Modell.|Atlbase.h|  
|[CAtlBaseModule](../../atl/reference/catlbasemodule-class.md)|Diese Klasse ist in jedem ATL-Projekt instanziiert.|atlcore.h|  
|[CAtlComModule](../../atl/reference/catlcommodule-class.md)|Diese Klasse implementiert, ein COM-Server-Modul.|Atlbase.h|  
|[CAtlDebugInterfacesModule](../../atl/reference/catldebuginterfacesmodule-class.md)|Diese Klasse bietet Unterstützung für das Debuggen von Schnittstellen.|Atlbase.h|  
|[CAtlDllModuleT](../../atl/reference/catldllmodulet-class.md)|Diese Klasse stellt das Modul für eine DLL.|Atlbase.h|  
|[CAtlException](../../atl/reference/catlexception-class.md)|Diese Klasse definiert eine ATL-Ausnahme.|atlexcept.h|  
|[CAtlExeModuleT](../../atl/reference/catlexemodulet-class.md)|Diese Klasse stellt das Modul für eine Anwendung.|Atlbase.h|  
|[CAtlFile](../../atl/reference/catlfile-class.md)|Diese Klasse stellt einen einfachen Wrapper für die Windows-Datei zur Behandlung von API.|atlfile.h|  
|[CAtlFileMapping](../../atl/reference/catlfilemapping-class.md)|Diese Klasse stellt eine Speicherabbilddatei, die Methoden der Cast-Operator hinzugefügt [CAtlFileMappingBase](../../atl/reference/catlfilemappingbase-class.md).|atlfile.h|  
|[CAtlFileMappingBase](../../atl/reference/catlfilemappingbase-class.md)|Diese Klasse stellt eine Datei mit zugewiesenem Speicher.|atlfile.h|  
|[CAtlList](../../atl/reference/catllist-class.md)|Diese Klasse stellt Methoden zum Erstellen und verwalten ein List-Objekt.|atlcoll.h|  
|[CAtlMap](../../atl/reference/catlmap-class.md)|Diese Klasse stellt Methoden zum Erstellen und Verwalten von einem Map-Objekt.|atlcoll.h|  
|[CAtlModule](../../atl/reference/catlmodule-class.md)|Diese Klasse stellt die Methoden, die durch verschiedene ATL-Modulklassen verwendet.|Atlbase.h|  
|[CAtlModuleT](../../atl/reference/catlmodulet-class.md)|Diese Klasse implementiert ein ATL-Modul.|Atlbase.h|  
|[CAtlPreviewCtrlImpl](../../atl/reference/catlpreviewctrlimpl-class.md)|Diese Klasse ist eine ATL-Implementierung eines Fensters, das auf ein Hostfenster, bereitgestellt von der Shell for Rich Preview eingefügt wird.|atlpreviewctrlimpl.h|  
|[CAtlServiceModuleT](../../atl/reference/catlservicemodulet-class.md)|Diese Klasse implementiert, einen Dienst.|Atlbase.h|  
|[CAtlTemporaryFile](../../atl/reference/catltemporaryfile-class.md)|Diese Klasse stellt Methoden bereit, für die Erstellung und Verwendung einer temporären Datei.|atlfile.h|  
|[CAtlTransactionManager](../../atl/reference/catltransactionmanager-class.md)|Diese Klasse stellt einen Wrapper für die Funktionen des Kerneltransaktions-Manager (KTM).|atltransactionmanager.h|  
|[CAtlWinModule](../../atl/reference/catlwinmodule-class.md)|Diese Klasse bietet Unterstützung für ATL-Windowing-Komponenten.|Atlbase.h|  
|[CAutoPtr](../../atl/reference/cautoptr-class.md)|Diese Klasse stellt einen intelligenten Zeiger-Objekt.|Atlbase.h|  
|[CAutoPtrArray](../../atl/reference/cautoptrarray-class.md)|Diese Klasse stellt die Methoden, die nützlich, wenn Sie ein Array von intelligenten Zeigern zu erstellen.|Atlbase.h|  
|[CAutoPtrElementTraits](../../atl/reference/cautoptrelementtraits-class.md)|Diese Klasse stellt die Methoden, statische Funktionen und Typdefinitionen hilfreich zum Erstellen von Sammlungen von intelligenten Zeigern.|atlcoll.h|  
|[CAutoPtrList](../../atl/reference/cautoptrlist-class.md)|Diese Klasse stellt nützliche Methoden aus, wenn Sie eine Liste von intelligenten Zeigern zu erstellen.|atlcoll.h|  
|[CAutoVectorPtr](../../atl/reference/cautovectorptr-class.md)|Diese Klasse stellt ein intelligenter Zeiger-Objekt, das mit der neuen Vektor dar und delete-Operator.|Atlbase.h|  
|[CAutoVectorPtrElementTraits](../../atl/reference/cautovectorptrelementtraits-class.md)|Diese Klasse stellt die Methoden, statische Funktionen und Typdefinitionen hilfreich beim Erstellen von Sammlungen von intelligenten Zeigern, die mit der neuen Vektor und "delete".|atlcoll.h|  
|[CAxDialogImpl](../../atl/reference/caxdialogimpl-class.md)|Diese Klasse implementiert ein Dialogfeld (gebunden oder ungebunden), die ActiveX-Steuerelemente hostet.|atlwin.h vorhanden|  
|[CAxWindow](../../atl/reference/caxwindow-class.md)|Diese Klasse stellt Methoden zum Bearbeiten eines Fensters, das Hosten eines ActiveX-Steuerelements.|atlwin.h vorhanden|  
|[CAxWindow2T](../../atl/reference/caxwindow2t-class.md)|Diese Klasse stellt Methoden zum Bearbeiten eines Fensters, das ein ActiveX-Steuerelement hostet und auch Unterstützung für das Hosten von lizenzierter ActiveX-Steuerelementen.|atlwin.h vorhanden|  
|[CBindStatusCallback](../../atl/reference/cbindstatuscallback-class.md)|Diese Klasse implementiert die `IBindStatusCallback`-Schnittstelle.|atlctl.h|  
|[CComAggObject](../../atl/reference/ccomaggobject-class.md)|Diese Klasse implementiert [IUnknown](/windows/desktop/api/unknwn/nn-unknwn-iunknown) für ein zusammengesetztes Objekt.|Atlcom.h|  
|[CComAllocator](../../atl/reference/ccomallocator-class.md)|Diese Klasse stellt Methoden zum Verwalten von Speicher mithilfe von COM-Arbeitsspeicher-Routinen.|Atlbase.h|  
|[CComApartment](../../atl/reference/ccomapartment-class.md)|Diese Klasse bietet Unterstützung für die Verwaltung von einem Apartment in einem Thread Pooling-EXE-Modul.|Atlbase.h|  
|[CComAutoCriticalSection](../../atl/reference/ccomautocriticalsection-class.md)|Diese Klasse stellt Methoden zum Abrufen und Freigeben des Besitzes eines kritischen Abschnitts-Objekts.|atlcore.h|  
|[CComAutoThreadModule](../../atl/reference/ccomautothreadmodule-class.md)|Zum Zeitpunkt der ATL 7.0 `CComAutoThreadModule` ist veraltet: finden Sie unter [ATL-Module](../../atl/atl-module-classes.md) Weitere Details.|Atlbase.h|  
|[CComBSTR](../../atl/reference/ccombstr-class.md)|Diese Klasse ist ein Wrapper für BSTR.|Atlbase.h|  
|[CComCachedTearOffObject](../../atl/reference/ccomcachedtearoffobject-class.md)|Diese Klasse implementiert [IUnknown](/windows/desktop/api/unknwn/nn-unknwn-iunknown) für eine Tearoff Schnittstelle.|Atlcom.h|  
|[CComClassFactory](../../atl/reference/ccomclassfactory-class.md)|Diese Klasse implementiert die [IClassFactory](/windows/desktop/api/unknwnbase/nn-unknwnbase-iclassfactory) Schnittstelle.|Atlcom.h|  
|[CComClassFactory2](../../atl/reference/ccomclassfactory2-class.md)|Diese Klasse implementiert die [IClassFactory2](/windows/desktop/api/ocidl/nn-ocidl-iclassfactory2) Schnittstelle.|Atlcom.h|  
|[CComClassFactoryAutoThread](../../atl/reference/ccomclassfactoryautothread-class.md)|Diese Klasse implementiert die [IClassFactory](/windows/desktop/api/unknwnbase/nn-unknwnbase-iclassfactory) Schnittstelle und ermöglicht es Objekten, die in mehreren Apartments erstellt werden.|Atlcom.h|  
|[CComClassFactorySingleton](../../atl/reference/ccomclassfactorysingleton-class.md)|Diese Klasse wird von [CComClassFactory](../../atl/reference/ccomclassfactory-class.md) und verwendet [CComObjectGlobal](../../atl/reference/ccomobjectglobal-class.md) um ein einzelnes Objekt zu erstellen.|Atlcom.h|  
|[CComCoClass](../../atl/reference/ccomcoclass-class.md)|Diese Klasse stellt Methoden zum Erstellen von Instanzen einer Klasse und ihre Eigenschaften abrufen.|Atlcom.h|  
|[CComCompositeControl](../../atl/reference/ccomcompositecontrol-class.md)|Diese Klasse stellt die Methoden erforderlich, um ein zusammengesetztes Steuerelement zu implementieren.|atlctl.h|  
|[CComContainedObject](../../atl/reference/ccomcontainedobject-class.md)|Diese Klasse implementiert [IUnknown](/windows/desktop/api/unknwn/nn-unknwn-iunknown) delegiert Vorgänge an den des Besitzerobjekts `IUnknown`.|Atlcom.h|  
|[CComControl](../../atl/reference/ccomcontrol-class.md)|Diese Klasse stellt Methoden zum Erstellen und Verwalten von ATL-Steuerelementen.|atlctl.h|  
|[CComControlBase](../../atl/reference/ccomcontrolbase-class.md)|Diese Klasse stellt Methoden zum Erstellen und Verwalten von ATL-Steuerelementen.|atlctl.h|  
|[CComCriticalSection](../../atl/reference/ccomcriticalsection-class.md)|Diese Klasse stellt Methoden zum Abrufen und Freigeben des Besitzes eines kritischen Abschnitts-Objekts.|atlcore.h|  
|[CComCritSecLock](../../atl/reference/ccomcritseclock-class.md)|Diese Klasse stellt Methoden zum Sperren und Entsperren von einem kritischen Abschnittsobjekt.|Atlbase.h|  
|[CComCurrency](../../atl/reference/ccomcurrency-class.md)|Diese Klasse verfügt über Methoden und Operatoren zum Erstellen und Verwalten eines CURRENCY-Objekts ist.|"atlcur.h"|  
|[CComDynamicUnkArray](../../atl/reference/ccomdynamicunkarray-class.md)|Diese Klasse speichert ein Array von `IUnknown` Zeiger.|Atlcom.h|  
|[CComEnum](../../atl/reference/ccomenum-class.md)|Diese Klasse definiert ein COM-Enumerator-Objekt basierend auf einem Wertearray.|Atlcom.h|  
|[CComEnumImpl](../../atl/reference/ccomenumimpl-class.md)|Diese Klasse stellt die Implementierung für eine COM-Enumerator-Schnittstelle, in dem die Elemente, die aufgezählt werden in einem Array gespeichert werden.|Atlcom.h|  
|[CComEnumOnSTL](../../atl/reference/ccomenumonstl-class.md)|Diese Klasse definiert ein COM-Enumerator-Objekt auf Grundlage einer C++-Standardbibliothek-Auflistung.|Atlcom.h|  
|[CComFakeCriticalSection](../../atl/reference/ccomfakecriticalsection-class.md)|Diese Klasse stellt die gleichen Methoden wie [CComCriticalSection](../../atl/reference/ccomcriticalsection-class.md) jedoch kein kritischen Abschnitts.|atlcore.h|  
|[CComGITPtr](../../atl/reference/ccomgitptr-class.md)|Diese Klasse stellt Methoden für den Umgang mit Schnittstellenzeiger und der globale Schnittstellentabelle (GIT).|Atlbase.h|  
|[CComHeap](../../atl/reference/ccomheap-class.md)|Diese Klasse implementiert [IAtlMemMgr](../../atl/reference/iatlmemmgr-class.md) mithilfe der COM-speicherbelegungsfunktionen.|ATLComMem.h|  
|[CComHeapPtr](../../atl/reference/ccomheapptr-class.md)|Eine intelligente Zeiger-Klasse für die Verwaltung von Heap-Zeiger.|Atlbase.h|  
|[CComModule](../../atl/reference/ccommodule-class.md)|Zum Zeitpunkt der ATL 7.0 `CComModule` ist veraltet: finden Sie unter [ATL-Module](../../atl/atl-module-classes.md) Weitere Details.|Atlbase.h|  
|[CComMultiThreadModel](../../atl/reference/ccommultithreadmodel-class.md)|Diese Klasse stellt den Wert einer Variablen threadsichere Methoden zum Inkrementieren und dekrementieren.|Atlbase.h|  
|[CComMultiThreadModelNoCS](../../atl/reference/ccommultithreadmodelnocs-class.md)|Diese Klasse stellt die threadsichere Methoden für inkrementiert und dekrementiert den Wert einer Variablen, ohne den kritischen Abschnitt zu sperren oder Entsperren Funktionen.|Atlbase.h|  
|[CComObject](../../atl/reference/ccomobject-class.md)|Diese Klasse implementiert `IUnknown` für einen zusammengesetzten Objekt.|Atlcom.h|  
|[CComObjectGlobal](../../atl/reference/ccomobjectglobal-class.md)|Diese Klasse verwaltet einen Verweiszähler für das Modul mit Ihrem `Base` Objekt.|Atlcom.h|  
|[CComObjectNoLock](../../atl/reference/ccomobjectnolock-class.md)|Diese Klasse implementiert `IUnknown` eines zusammengesetzten Objekts, aber wird nicht erhöhen, die die Sperrenanzahl Modul im Konstruktor.|Atlcom.h|  
|[CComObjectRoot](../../atl/reference/ccomobjectroot-class.md)|Diese Typdefinition der [CComObjectRootEx](../../atl/reference/ccomobjectrootex-class.md) ist auf dem standardmäßigen threading-Modell des Servers vorlagenbasiert.|Atlcom.h|  
|[CComObjectRootEx](../../atl/reference/ccomobjectrootex-class.md)|Diese Klasse stellt Methoden zur Behandlung von Objekt Anzahl verweisverwaltung für aggregierte und zusammengesetzten Objekte.|Atlcom.h|  
|[CComObjectStack](../../atl/reference/ccomobjectstack-class.md)|Diese Klasse erstellt ein temporäre COM-Objekt, und bietet es eine skeletal-Implementierung der `IUnknown`.|Atlcom.h|  
|[CComPolyObject](../../atl/reference/ccompolyobject-class.md)|Diese Klasse implementiert `IUnknown` für ein Objekt zusammengesetzten oder aggregiert.|Atlcom.h|  
|[CComPtr](../../atl/reference/ccomptr-class.md)|Eine intelligente Zeiger-Klasse für die Verwaltung von COM-Schnittstellenzeiger.|"atlcomcli.h"|  
|[CComPtrBase](../../atl/reference/ccomptrbase-class.md)|Diese Klasse bietet eine Grundlage für intelligente Zeiger-Klassen, die mit COM-basierten Speicher Routinen.|"atlcomcli.h"|  
|[CComQIPtr](../../atl/reference/ccomqiptr-class.md)|Eine intelligente Zeiger-Klasse für die Verwaltung von COM-Schnittstellenzeiger.|"atlcomcli.h"|  
|[CComQIPtrElementTraits](../../atl/reference/ccomqiptrelementtraits-class.md)|Diese Klasse stellt die Methoden, statische Funktionen und Typdefinitionen hilfreich zum Erstellen von Sammlungen von COM-Schnittstellenzeiger.|atlcoll.h|  
|[CComSafeArray](../../atl/reference/ccomsafearray-class.md)|Diese Klasse ist ein Wrapper für die `SAFEARRAY Data Type` Struktur.|atlsafe.h|  
|[CComSafeArrayBound](../../atl/reference/ccomsafearraybound-class.md)|Diese Klasse ist ein Wrapper für eine `SAFEARRAYBOUND` Struktur.|atlsafe.h|  
|[CComSimpleThreadAllocator](../../atl/reference/ccomsimplethreadallocator-class.md)|Diese Klasse verwaltet die threadauswahl für die Klasse [CComAutoThreadModule](../../atl/reference/ccomautothreadmodule-class.md).|Atlbase.h|  
|[CComSingleThreadModel](../../atl/reference/ccomsinglethreadmodel-class.md)|Diese Klasse stellt Methoden zum Inkrementieren und Dekrementieren den Wert einer Variablen zu.|Atlbase.h|  
|[CComTearOffObject](../../atl/reference/ccomtearoffobject-class.md)|Diese Klasse implementiert eine Tearoff Schnittstelle.|Atlcom.h|  
|[CComUnkArray](../../atl/reference/ccomunkarray-class.md)|Diese Klasse speichert `IUnknown` Zeiger als Parameter verwendet werden soll, und die [IConnectionPointImpl](../../atl/reference/iconnectionpointimpl-class.md) Vorlagenklasse.|Atlcom.h|  
|[CComVariant](../../atl/reference/ccomvariant-class.md)|Diese Klasse umschließt den VARIANT-Datentyp, der einen Member, der angibt, der den Typ der gespeicherten Daten bereitstellt.|"atlcomcli.h"|  
|[CContainedWindowT](../../atl/reference/ccontainedwindowt-class.md)|Diese Klasse implementiert ein Fenster in einem anderen Objekt enthalten sind.|atlwin.h vorhanden|  
|[CCRTAllocator](../../atl/reference/ccrtallocator-class.md)|Diese Klasse stellt Methoden zum Verwalten von Speicher mithilfe von CRT-Arbeitsspeicher-Routinen.|atlcore.h|  
|[CCRTHeap](../../atl/reference/ccrtheap-class.md)|Diese Klasse implementiert [IAtlMemMgr](../../atl/reference/iatlmemmgr-class.md) mithilfe der Funktionen der CRT-Heap.|atlmem.h|  
|[CDacl](../../atl/reference/cdacl-class.md)|Diese Klasse ist ein Wrapper für eine DACL (discretionary Access Control List)-Struktur.|ATLSecurity.h|  
|[CDebugReportHook-Klasse](../../atl/reference/cdebugreporthook-class.md)|Verwenden Sie diese Klasse zum Senden von debugberichten und einer named Pipe an.|"atlutil.h"|  
|[CDefaultCharTraits](../../atl/reference/cdefaultchartraits-class.md)|Diese Klasse stellt zwei statische Funktionen zum Konvertieren von Zeichen zwischen Groß- und Kleinbuchstaben.|atlcoll.h|  
|[CDefaultCompareTraits](../../atl/reference/cdefaultcomparetraits-class.md)|Diese Klasse stellt die standardmäßige Element Vergleichsfunktionen.|atlcoll.h|  
|[CDefaultElementTraits](../../atl/reference/cdefaultelementtraits-class.md)|Diese Klasse stellt die Standardmethoden und -Funktionen, damit eine Auflistungsklasse.|atlcoll.h|  
|[CDefaultHashTraits](../../atl/reference/cdefaulthashtraits-class.md)|Diese Klasse stellt eine statische Funktion zum Berechnen der Hashwerte.|atlcoll.h|  
|[CDialogImpl](../../atl/reference/cdialogimpl-class.md)|Diese Klasse stellt Methoden zum Erstellen ein modales oder nicht modales Dialogfeld an.|atlwin.h vorhanden|  
|[CDynamicChain](../../atl/reference/cdynamicchain-class.md)|Diese Klasse stellt die Methoden, die Sie unterstützen die dynamische Verkettung von meldungszuordnungen bereit.|atlwin.h vorhanden|  
|[CElementTraits](../../atl/reference/celementtraits-class.md)|Diese Klasse wird von Auflistungsklassen verwendet, verschieben, kopieren, Vergleich und Hashvorgängen Methoden und Funktionen bereit.|atlcoll.h|  
|[CElementTraitsBase](../../atl/reference/celementtraitsbase-class.md)|Diese Klasse bietet standardmäßige kopieren und verschieben die Methoden, damit eine Auflistungsklasse.|atlcoll.h|  
|[CFirePropNotifyEvent](../../atl/reference/cfirepropnotifyevent-class.md)|Diese Klasse stellt Methoden für die Benachrichtigung des Containers-Senke in Bezug auf Änderungen von Steuerelement-Eigenschaften.|atlctl.h|  
|[CGlobalHeap](../../atl/reference/cglobalheap-class.md)|Diese Klasse implementiert [IAtlMemMgr](../../atl/reference/iatlmemmgr-class.md) mithilfe der Win32-Heap der globalen Funktionen.|atlmem.h|  
|[CHandle](../../atl/reference/chandle-class.md)|Diese Klasse stellt Methoden zum Erstellen und Verwenden eines Handleobjekts.|Atlbase.h|  
|[CHeapPtr](../../atl/reference/cheapptr-class.md)|Eine intelligente Zeiger-Klasse für die Verwaltung von Heap-Zeiger.|atlcore.h|  
|[CHeapPtrBase](../../atl/reference/cheapptrbase-class.md)|Diese Klasse bildet die Grundlage für mehrere Klassen von smart-Heap-Zeiger.|atlcore.h|  
|[CHeapPtrElementTraits-Klasse](../../atl/reference/cheapptrelementtraits-class.md)|Diese Klasse stellt die Methoden, statische Funktionen und Typdefinitionen hilfreich zum Erstellen von Sammlungen von Heap-Zeigern.|atlcoll.h|  
|[CHeapPtrList](../../atl/reference/cheapptrlist-class.md)|Diese Klasse stellt nützliche Methoden beim Erstellen einer Liste von Heap-Zeigern.|atlcoll.h|  
|[CImage](../../atl-mfc-shared/reference/cimage-class.md)|Bietet erweiterte Bitmapunterstützung, einschließlich der Möglichkeit zum Laden und Speichern von Bildern in JPEG, GIF, BMP und Portable Network Graphics (PNG).|atlimage.h|  
|[CInterfaceArray](../../atl/reference/cinterfacearray-class.md)|Diese Klasse stellt nützliche Methoden aus, wenn Sie ein Array von COM-Schnittstellenzeiger zu erstellen.|atlcoll.h|  
|[CInterfaceList](../../atl/reference/cinterfacelist-class.md)|Diese Klasse stellt nützliche Methoden aus, wenn Sie eine Liste der COM-Schnittstellenzeiger zu erstellen.|atlcoll.h|  
|[Clocalheap –](../../atl/reference/clocalheap-class.md)|Diese Klasse implementiert [IAtlMemMgr](../../atl/reference/iatlmemmgr-class.md) mithilfe der Win32-Funktionen lokalen Heap befindet.|atlmem.h|  
|[CMessageMap](../../atl/reference/cmessagemap-class.md)|Diese Klasse ermöglicht, dass ein Objekt der Nachricht Zuordnungen enthalten, die von einem anderen Objekt zugegriffen werden.|atlwin.h vorhanden|  
|[CNonStatelessWorker-Klasse](../../atl/reference/cnonstatelessworker-class.md)|Empfängt Anforderungen aus dem Threadpool und übergibt sie an eine Worker-Objekt, das erstellt und zerstört wird bei jeder Anforderung.|"atlutil.h"|  
|[CNoWorkerThread-Klasse](../../atl/reference/cnoworkerthread-class.md)|Verwenden Sie diese Klasse als Argument für die `MonitorClass` Parameter Vorlagencache Klassen, wenn Sie dynamische Cache Wartung deaktivieren möchten.|"atlutil.h"|  
|[CPathT-Klasse](../../atl/reference/cpatht-class.md)|Diese Klasse stellt einen Pfad an.|"atlpath.h"|  
|[CPrimitiveElementTraits](../../atl/reference/cprimitiveelementtraits-class.md)|Diese Klasse stellt die Standardmethoden und -Funktionen für eine Auflistungsklasse bestehend aus primitiven Datentypen.|atlcoll.h|  
|[CPrivateObjectSecurityDesc](../../atl/reference/cprivateobjectsecuritydesc-class.md)|Diese Klasse stellt ein privates Objekt sicherheitsbeschreibungs-Objekt.|ATLSecurity.h|  
|[CRBMap](../../atl/reference/crbmap-class.md)|Diese Klasse stellt eine Zuordnungsstruktur, indem Sie eine binäre Rot-Schwarz-Baum.|atlcoll.h|  
|[CRBMultiMap](../../atl/reference/crbmultimap-class.md)|Diese Klasse stellt eine Zuordnungsstruktur, die einzelnen Schlüssel mit mehr als einem Wert, mit einer binären Rot-Schwarz-Struktur verknüpft werden kann.|atlcoll.h|  
|[CRBTree](../../atl/reference/crbtree-class.md)|Diese Klasse stellt Methoden zum Erstellen und nutzen ein Rot-Schwarz-Baum.|atlcoll.h|  
|[CRegKey](../../atl/reference/cregkey-class.md)|Diese Klasse stellt Methoden zum Bearbeiten der Einträge in der systemregistrierung.|Atlbase.h|  
|[CRTThreadTraits](../../atl/reference/crtthreadtraits-class.md)|Diese Klasse stellt die Erstellungsfunktion für einen Thread CRT. Verwenden Sie diese Klasse aus, wenn der Thread die CRT-Funktionen verwenden möchten.|Atlbase.h|  
|[CSacl](../../atl/reference/csacl-class.md)|Diese Klasse ist ein Wrapper für eine SACL (System Access Control List)-Struktur.|ATLSecurity.h|  
|[CSecurityAttributes](../../atl/reference/csecurityattributes-class.md)|Diese Klasse ist ein einfacher Wrapper für die `SECURITY_ATTRIBUTES` Struktur.|ATLSecurity.h|  
|[CSecurityDesc](../../atl/reference/csecuritydesc-class.md)|Diese Klasse ist ein Wrapper für die `SECURITY_DESCRIPTOR` Struktur.|ATLSecurity.h|  
|[CSid](../../atl/reference/csid-class.md)|Diese Klasse ist ein Wrapper für eine `SID` -Struktur (Sicherheits-ID).|ATLSecurity.h|  
|[CSimpleArray](../../atl/reference/csimplearray-class.md)|Diese Klasse stellt Methoden zum Verwalten von einem einfachen Array an.|atlsimpcoll.h|  
|[CSimpleArrayEqualHelper](../../atl/reference/csimplearrayequalhelper-class.md)|Diese Klasse ist eine Hilfsklasse für die [CSimpleArray](../../atl/reference/csimplearray-class.md) Klasse.|atlsimpcoll.h|  
|[CSimpleArrayEqualHelperFalse](../../atl/reference/csimplearrayequalhelperfalse-class.md)|Diese Klasse ist eine Hilfsklasse für die [CSimpleArray](../../atl/reference/csimplearray-class.md) Klasse.|atlsimpcoll.h|  
|[CSimpleDialog](../../atl/reference/csimpledialog-class.md)|Diese Klasse implementiert die grundlegende modales Dialogfeld.|atlwin.h vorhanden|  
|[CSimpleMap](../../atl/reference/csimplemap-class.md)|Diese Klasse bietet Unterstützung für eine einfache Zuordnung-Array.|atlsimpcoll.h|  
|[CSimpleMapEqualHelper](../../atl/reference/csimplemapequalhelper-class.md)|Diese Klasse ist eine Hilfsklasse für die [CSimpleMap](../../atl/reference/csimplemap-class.md) Klasse.|atlsimpcoll.h|  
|[CSimpleMapEqualHelperFalse](../../atl/reference/csimplemapequalhelperfalse-class.md)|Diese Klasse ist eine Hilfsklasse für die [CSimpleMap](../../atl/reference/csimplemap-class.md) Klasse.|atlsimpcoll.h|  
|[CSnapInItemImpl](../../atl/reference/csnapinitemimpl-class.md)|Diese Klasse stellt Methoden zum Implementieren eines-Snap-in-Node-Objekts.|atlsnap.h|  
|[CSnapInPropertyPageImpl](../../atl/reference/csnapinpropertypageimpl-class.md)|Diese Klasse stellt Methoden zum Implementieren einer Snap-in-Eigenschaft-Page-Objekt.|atlsnap.h|  
|[CStockPropImpl](../../atl/reference/cstockpropimpl-class.md)|Diese Klasse stellt Methoden zur Unterstützung der vordefinierten Werte.|atlctl.h|  
|[CStringElementTraits](../../atl/reference/cstringelementtraits-class.md)|Diese Klasse stellt statische Funktionen, die durch das Speichern von Auflistungsklassen verwendet `CString` Objekte.|CStringT.h|  
|[CStringElementTraitsI](../../atl/reference/cstringelementtraitsi-class.md)|Diese Klasse stellt statische Funktionen, die im Zusammenhang mit Zeichenfolgen, die in der Auflistung von Klassenobjekten gespeichert. Sie ähnelt damit [CStringElementTraits](../../atl/reference/cstringelementtraits-class.md), aber die Groß-/Kleinschreibung Vergleiche ausgeführt.|atlcoll.h|  
|[CStringRefElementTraits](../../atl/reference/cstringrefelementtraits-class.md)|Diese Klasse stellt statische Funktionen, die im Zusammenhang mit Zeichenfolgen, die in der Auflistung von Klassenobjekten gespeichert. Der String-Objekte werden als Verweise behandelt.|atlcoll.h|  
|[CThreadPool-Klasse](../../atl/reference/cthreadpool-class.md)|Diese Klasse stellt einen Pool von Arbeitsthreads, die eine Warteschlange von Arbeitsaufgaben zu verarbeiten.|"atlutil.h"|  
|[CTokenGroups](../../atl/reference/ctokengroups-class.md)|Diese Klasse ist ein Wrapper für die `TOKEN_GROUPS` Struktur.|ATLSecurity.h|  
|[CTokenPrivileges](../../atl/reference/ctokenprivileges-class.md)|Diese Klasse ist ein Wrapper für die `TOKEN_PRIVILEGES` Struktur.|ATLSecurity.h|  
|[CUrl-Klasse](../../atl/reference/curl-class.md)|Diese Klasse stellt eine URL an. Sie können jedes Element der unabhängig von den anderen-URL ändern, ob eine vorhandene URL analysieren Zeichenfolge oder eine Zeichenfolge von Grund auf neu erstellen.|"atlutil.h"|  
|[CW2AEX](../../atl/reference/cw2aex-class.md)|Diese Klasse wird von der Zeichenfolgen-konvertierungsmakros CT2AEX, CW2TEX, CW2CTEX, CT2CAEX wird und der Typedef CW2A verwendet.|atlconv.h|  
|[CW2CWEX](../../atl/reference/cw2cwex-class.md)|Diese Klasse wird von der Zeichenfolgen-konvertierungsmakros CW2CTEX und CT2CWEX und der Typedef CW2CW verwendet.|atlconv.h|  
|[CW2WEX](../../atl/reference/cw2wex-class.md)|Diese Klasse wird von der Zeichenfolgen-konvertierungsmakros CW2TEX und CT2WEX und der Typedef CW2W verwendet.|atlconv.h|  
|[CWin32Heap](../../atl/reference/cwin32heap-class.md)|Diese Klasse implementiert [IAtlMemMgr](../../atl/reference/iatlmemmgr-class.md) mithilfe der Win32-Heapreservierungsfunktionen.|atlmem.h|  
|[CWindow](../../atl/reference/cwindow-class.md)|Diese Klasse stellt Methoden zum Bearbeiten eines Fensters bereit.|atlwin.h vorhanden|  
|[CWindowImpl](../../atl/reference/cwindowimpl-class.md)|Diese Klasse stellt Methoden zum Erstellen oder Unterklassen eines Fensters bereit.|atlwin.h vorhanden|  
|[CWinTraits](../../atl/reference/cwintraits-class.md)|Diese Klasse stellt eine Methode für die Standardisierung der Stile, die beim Erstellen eines Objekts im Fenster verwendet.|atlwin.h vorhanden|  
|[CWinTraitsOR](../../atl/reference/cwintraitsor-class.md)|Diese Klasse stellt eine Methode für die Standardisierung der Stile, die beim Erstellen eines Objekts im Fenster verwendet.|atlwin.h vorhanden|  
|[CWndClassInfo](../../atl/reference/cwndclassinfo-class.md)|Diese Klasse stellt Methoden zum Erfassen von Informationen für eine Fensterklasse.|atlwin.h vorhanden|  
|[CWorkerThread-Klasse](../../atl/reference/cworkerthread-class.md)|Diese Klasse einen Arbeitsthread erstellt oder verwendet eine vorhandene, wartet auf eine oder mehrere Kernel-Objekt-Handles und führt eine angegebene Client-Funktion aus, wenn einem der Handles signalisiert wird.|"atlutil.h"|  
|[IAtlAutoThreadModule](../../atl/reference/iatlautothreadmodule-class.md)|Diese Klasse stellt eine Schnittstelle für eine `CreateInstance` Methode.|Atlbase.h|  
|[IAtlMemMgr](../../atl/reference/iatlmemmgr-class.md)|Diese Klasse stellt die Schnittstelle, um einen Speicher-Manager.|atlmem.h|  
|[IAxWinAmbientDispatch](../../atl/reference/iaxwinambientdispatch-interface.md)|Diese Schnittstelle stellt Methoden zur Angabe der Merkmale des gehosteten Steuerelements oder des Containers.|Atlbase.h, konnte IRegistrar|  
|[IAxWinAmbientDispatchEx](../../atl/reference/iaxwinambientdispatchex-interface.md)|Diese Schnittstelle implementiert, ergänzende Ambiente-Eigenschaften für ein gehostetes Steuerelement.|Atlbase.h, konnte IRegistrar|  
|[IAxWinHostWindow](../../atl/reference/iaxwinhostwindow-interface.md)|Diese Schnittstelle bietet Methoden zum Bearbeiten eines Steuerelements und dem zugehörigen Hostobjekt.|Atlbase.h, konnte IRegistrar|  
|[IAxWinHostWindowLic](../../atl/reference/iaxwinhostwindowlic-interface.md)|Diese Schnittstelle bietet Methoden zum Bearbeiten von ein lizenziertes Steuerelement und dessen Host-Objekt.|Atlbase.h, konnte IRegistrar|  
|[ICollectionOnSTLImpl](../../atl/reference/icollectiononstlimpl-class.md)|Diese Klasse stellt die Methoden, die von einer Auflistungsklasse.|Atlcom.h|  
|[IConnectionPointContainerImpl](../../atl/reference/iconnectionpointcontainerimpl-class.md)|Diese Klasse implementiert eine Verbindungspunktcontainer zur Verwaltung einer Auflistung von [IConnectionPointImpl](../../atl/reference/iconnectionpointimpl-class.md) Objekte.|Atlcom.h|  
|[IConnectionPointImpl](../../atl/reference/iconnectionpointimpl-class.md)|Diese Klasse implementiert einen Verbindungspunkt.|Atlcom.h|  
|[IDataObjectImpl](../../atl/reference/idataobjectimpl-class.md)|Diese Klasse stellt Methoden für die Unterstützung, Uniform Data Transfer und Verwalten von Verbindungen.|atlctl.h|  
|[IDispatchImpl](../../atl/reference/idispatchimpl-class.md)|Diese Klasse stellt eine Standardimplementierung für die `IDispatch` Teil eine duale Schnittstelle.|Atlcom.h|  
|[IDispEventImpl](../../atl/reference/idispeventimpl-class.md)|Diese Klasse stellt Implementierungen von der `IDispatch` Methoden.|Atlcom.h|  
|[IDispEventSimpleImpl](../../atl/reference/idispeventsimpleimpl-class.md)|Diese Klasse stellt Implementierungen von der `IDispatch` Methoden ohne das Abrufen von Typinformationen aus einer Typbibliothek.|Atlcom.h|  
|[IDocHostUIHandlerDispatch](../../atl/reference/idochostuihandlerdispatch-interface.md)|Eine Schnittstelle, die Microsoft-HTML-Analyse- und -Rendering-Engine.|Atlbase.h, konnte IRegistrar|  
|[IEnumOnSTLImpl](../../atl/reference/ienumonstlimpl-class.md)|Diese Klasse definiert eine Enumeratorschnittstelle, die auf Grundlage einer C++-Standardbibliothek-Auflistung.|Atlcom.h|  
|[IObjectSafetyImpl](../../atl/reference/iobjectsafetyimpl-class.md)|Diese Klasse stellt eine Standardimplementierung von der `IObjectSafety` Schnittstelle, damit kann einen Client zum Abrufen und Festlegen eines Objekts Sicherheitsstufen.|atlctl.h|  
|[IObjectWithSiteImpl](../../atl/reference/iobjectwithsiteimpl-class.md)|Diese Klasse stellt die Methoden, dass ein Objekt mit dem Standort kommunizieren.|Atlcom.h|  
|[IOleControlImpl](../../atl/reference/iolecontrolimpl-class.md)|Diese Klasse stellt eine Standardimplementierung von der `IOleControl` -Schnittstelle und implementiert `IUnknown`.|atlctl.h|  
|[IOleInPlaceActiveObjectImpl](../../atl/reference/ioleinplaceactiveobjectimpl-class.md)|Diese Klasse stellt Methoden für die Unterstützung der Kommunikation zwischen einem in-Place-Steuerelement und seinem Container.|atlctl.h|  
|[IOleInPlaceObjectWindowlessImpl](../../atl/reference/ioleinplaceobjectwindowlessimpl-class.md)|Diese Klasse implementiert `IUnknown` und bietet Methoden, die ein fensterloses Steuerelement, um fenstermeldungen zu empfangen und zur Teilnahme an Drag & Drop-Vorgänge zu ermöglichen.|atlctl.h|  
|[IOleObjectImpl](../../atl/reference/ioleobjectimpl-class.md)|Diese Klasse implementiert `IUnknown` und ist die Dienstprinzipale-Schnittstelle über die ein Container, die mit einem Steuerelement kommuniziert.|atlctl.h|  
|[IPerPropertyBrowsingImpl](../../atl/reference/iperpropertybrowsingimpl-class.md)|Diese Klasse implementiert `IUnknown` und ermöglicht es einem Client auf die Informationen in den Eigenschaftenseiten eines Objekts zugreifen.|atlctl.h|  
|[IPersistPropertyBagImpl](../../atl/reference/ipersistpropertybagimpl-class.md)|Diese Klasse implementiert `IUnknown` und ermöglicht einem Objekt, dessen Eigenschaften in einen vom Client bereitgestellter Eigenschaftenbehälter zu speichern.|Atlcom.h|  
|[IPersistStorageImpl](../../atl/reference/ipersiststorageimpl-class.md)|Diese Klasse implementiert die [IPersistStorage](/windows/desktop/api/objidl/nn-objidl-ipersiststorage) Schnittstelle.|Atlcom.h|  
|[IPersistStreamInitImpl](../../atl/reference/ipersiststreaminitimpl-class.md)|Diese Klasse implementiert `IUnknown` und stellt eine Standardimplementierung von der [IPersistStreamInit](/windows/desktop/api/ocidl/nn-ocidl-ipersiststreaminit) Schnittstelle.|Atlcom.h|  
|[IPointerInactiveImpl](../../atl/reference/ipointerinactiveimpl-class.md)|Diese Klasse implementiert `IUnknown` und [IPointerInactive](/windows/desktop/api/ocidl/nn-ocidl-ipointerinactive) Schnittstellenmethoden.|atlctl.h|  
|[IPropertyNotifySinkCP](../../atl/reference/ipropertynotifysinkcp-class.md)|Diese Klasse stellt die [IPropertyNotifySink](/windows/desktop/api/ocidl/nn-ocidl-ipropertynotifysink) Schnittstelle als Ausgangsschnittstelle auf einem verbindungsfähigen Objekt.|atlctl.h|  
|[IPropertyPage2Impl](../../atl/reference/ipropertypage2impl-class.md)|Diese Klasse implementiert `IUnknown` und erbt von der Standardimplementierung von [IPropertyPageImpl](../../atl/reference/ipropertypageimpl-class.md).|atlctl.h|  
|[IPropertyPageImpl](../../atl/reference/ipropertypageimpl-class.md)|Diese Klasse implementiert `IUnknown` und stellt eine Standardimplementierung von der [IPropertyPage](/windows/desktop/api/ocidl/nn-ocidl-ipropertypage) Schnittstelle.|atlctl.h|  
|[IProvideClassInfo2Impl](../../atl/reference/iprovideclassinfo2impl-class.md)|Diese Klasse stellt eine Standardimplementierung von der [IProvideClassInfo](/windows/desktop/api/ocidl/nn-ocidl-iprovideclassinfo) und [IProvideClassInfo2](/windows/desktop/api/ocidl/nn-ocidl-iprovideclassinfo2) Methoden.|Atlcom.h|  
|[IQuickActivateImpl](../../atl/reference/iquickactivateimpl-class.md)|Diese Klasse kombiniert die Initialisierung des Container-Steuerelements in einem einzigen Aufruf.|atlctl.h|  
|[IRunnableObjectImpl](../../atl/reference/irunnableobjectimpl-class.md)|Diese Klasse implementiert `IUnknown` und stellt eine Standardimplementierung von der [IRunnableObject](/windows/desktop/api/objidl/nn-objidl-irunnableobject) Schnittstelle.|atlctl.h|  
|[IServiceProviderImpl](../../atl/reference/iserviceproviderimpl-class.md)|Diese Klasse stellt eine Standardimplementierung von der `IServiceProvider` Schnittstelle.|Atlcom.h|  
|[ISpecifyPropertyPagesImpl](../../atl/reference/ispecifypropertypagesimpl-class.md)|Diese Klasse implementiert `IUnknown` und stellt eine Standardimplementierung von der [ISpecifyPropertyPages](/windows/desktop/api/ocidl/nn-ocidl-ispecifypropertypages) Schnittstelle.|Atlcom.h|  
|[ISupportErrorInfoImpl](../../atl/reference/isupporterrorinfoimpl-class.md)|Diese Klasse stellt eine Standardimplementierung von der `ISupportErrorInfo Interface` Schnittstelle und kann verwendet werden, wenn nur eine einzelne Schnittstelle Fehler bei einem Objekt generiert.|Atlcom.h|  
|[IThreadPoolConfig-Schnittstelle](../../atl/reference/ithreadpoolconfig-interface.md)|Diese Schnittstelle bietet Methoden zum Konfigurieren eines Threadpools.|"atlutil.h"|  
|[IViewObjectExImpl](../../atl/reference/iviewobjecteximpl-class.md)|Diese Klasse implementiert `IUnknown` und stellt standardimplementierungen der [IViewObject](/windows/desktop/api/oleidl/nn-oleidl-iviewobject), [IViewObject2](/windows/desktop/api/oleidl/nn-oleidl-iviewobject2), und [IViewObjectEx](/windows/desktop/api/ocidl/nn-ocidl-iviewobjectex) Schnittstellen.|atlctl.h|  
|[IWorkerThreadClient-Schnittstelle](../../atl/reference/iworkerthreadclient-interface.md)|`IWorkerThreadClient` ist die Schnittstelle implementiert, die von Clients von der [CWorkerThread](../../atl/reference/cworkerthread-class.md) Klasse.|"atlutil.h"|  
|[_U_MENUorID](../../atl/reference/u-menuorid-class.md)|Diese Klasse stellt den Wrapper für `CreateWindow` und `CreateWindowEx`.|atlwin.h vorhanden|  
|[_U_RECT](../../atl/reference/u-rect-class.md)|Dieses Argument-Adapterklasse ermöglicht `RECT` Zeigern oder verweisen auf eine Funktion übergeben werden, die im Hinblick auf Zeigern implementiert wird.|atlwin.h vorhanden|  
|[_U_STRINGorID](../../atl/reference/u-stringorid-class.md)|Dieses Argument-Adapterklasse ermöglicht entweder Ressourcennamen (LPCTSTRs) oder Ressourcen-IDs (jenem) an eine Funktion übergeben werden, ohne dass des Aufrufers die ID in eine Zeichenfolge, die mit dem Makro MAKEINTRESOURCE zu konvertieren.|atlwin.h vorhanden|  
|[Win32ThreadTraits](../../atl/reference/win32threadtraits-class.md)|Diese Klasse stellt die Erstellungsfunktion für einen Windows-Thread. Verwenden Sie diese Klasse aus, wenn der Thread nicht CRT-Funktionen nutzen.|Atlbase.h|  
  
## <a name="see-also"></a>Siehe auch  
 [ATL-COM-Desktop-Komponenten](../../atl/atl-com-desktop-components.md)   
 [Funktionen](../../atl/reference/atl-functions.md)   
 [Global Variables (Globale Variablen)](../../atl/reference/atl-global-variables.md)   
 [Typdefinitionen](../../atl/reference/atl-typedefs.md)   
 [Übersicht über die Klasse](../../atl/atl-class-overview.md)


