---
title: ATL-Klassen und-Strukturen | Microsoft-Dokumentation
ms.date: 05/03/2018
helpviewer_keywords:
- classes [C++], ATL
- ATL, classes
ms.assetid: 7da42e2d-ac84-4506-92bd-502a86d68bdc
ms.openlocfilehash: 2bf13700ada3284b8a32718d21971e89e30e5b76
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/15/2019
ms.locfileid: "69498050"
---
# <a name="atl-classes-and-structs"></a>ATL-Klassen und -Strukturen

Der Active Template Library (ATL) umfasst die folgenden Klassen und Strukturen. Eine bestimmte Klasse nach Kategorie finden Sie in der [Übersicht über die ATL-Klasse](../../atl/atl-class-overview.md).

|Klasse/Struktur|Beschreibung|Header Datei|
|-----------|-----------------|-----------------|
|[ATL_DRAWINFO](../../atl/reference/atl-drawinfo-structure.md)|Enthält Informationen, die zum Rendern verschiedener Ziele verwendet werden, z. b. Drucker, Metadateien oder ActiveX-Steuerelemente.|atlctl. h|
|[_AtlCreateWndData](../../atl/reference/atlcreatewnddata-structure.md)|Enthält klasseninstanzdaten in windowingcode in ATL.|atlbase. h|
|[_ATL_BASE_MODULE70](../../atl/reference/atl-base-module70-structure.md)|Wird von jedem Projekt verwendet, das ATL verwendet.|atlbase. h|
|[_ATL_COM_MODULE70](../../atl/reference/atl-com-module70-structure.md)|Wird von com-bezogenes Code in ATL verwendet.| atlbase. h|
|[_ATL_FUNC_INFO](../../atl/reference/atl-func-info-structure.md)|Enthält Typinformationen, die verwendet werden, um eine Methode oder Eigenschaft für eine dispinterface zu beschreiben.|Atlcom. h|
|[_ATL_MODULE70](../../atl/reference/atl-module70-structure.md)|Enthält Daten, die von jedem ATL-Modul verwendet werden.|atlbase. h|
|[_ATL_WIN_MODULE70](../../atl/reference/atl-win-module70-structure.md)|Wird von windowingcode in ATL verwendet.|atlbase. h|
|[CA2AEX](../../atl/reference/ca2aex-class.md)|Diese Klasse wird von den Zeichen folgen Konvertierungs Makros CA2TEX und CT2AEX sowie von typedef CA2A verwendet.|atlrev. h|
|[CA2CAEX](../../atl/reference/ca2caex-class.md)|Diese Klasse wird von Zeichen folgen Konvertierungs Makros CA2CTEX und CT2CAEX sowie von typedef CA2CA verwendet.|atlrev. h|
|[CA2WEX](../../atl/reference/ca2wex-class.md)|Diese Klasse wird von den Zeichen folgen Konvertierungs Makros CA2TEX, CA2CTEX, CT2WEX und CT2CWEX sowie von typedef CA2W verwendet.|atlrev. h|
|[CAccessToken](../../atl/reference/caccesstoken-class.md)|Diese Klasse ist ein Wrapper für ein Zugriffs Token.|ATLSecurity. h|
|[CaCl](../../atl/reference/cacl-class.md)|Diese Klasse ist ein Wrapper für eine ACL (Access-Control List)-Struktur.|ATLSecurity. h|
|[CAdapt](../../atl/reference/cadapt-class.md)|Diese Vorlage dient dazu, Klassen zu umschließen, die den Adressoperator so umdefinieren, dass eine andere als die Adresse des Objekts zurückgegeben wird.|atlcomcli. h|
|[CAtlArray](../../atl/reference/catlarray-class.md)|Diese Klasse implementiert ein Array Objekt.|atlcoll. h|
|[CAtlAutoThreadModule](../../atl/reference/catlautothreadmodule-class.md)|Diese Klasse implementiert einen com-Server mit einem Thread im Pool.|atlbase. h|
|[CAtlAutoThreadModuleT](../../atl/reference/catlautothreadmodulet-class.md)|Diese Klasse stellt Methoden zum Implementieren eines Thread Pool-com-Servers mit einem Thread Pool bereit.|atlbase. h|
|["" Für ""](../../atl/reference/catlbasemodule-class.md)|Diese Klasse wird in jedem ATL-Projekt instanziiert.|atlcore. h|
|[""-Modul](../../atl/reference/catlcommodule-class.md)|Diese Klasse implementiert ein com-Servermodul.|atlbase. h|
|[CAtlDebugInterfacesModule](../../atl/reference/catldebuginterfacesmodule-class.md)|Diese Klasse unterstützt das Debuggen von Schnittstellen.|atlbase. h|
|[CAtlDllModuleT](../../atl/reference/catldllmodulet-class.md)|Diese Klasse stellt das Modul für eine DLL dar.|atlbase. h|
|[-Ception](../../atl/reference/catlexception-class.md)|Diese Klasse definiert eine ATL-Ausnahme.|atlexcept. h|
|[CAtlExeModuleT](../../atl/reference/catlexemodulet-class.md)|Diese Klasse stellt das Modul für eine Anwendung dar.|atlbase. h|
|[CAtlFile](../../atl/reference/catlfile-class.md)|Diese Klasse stellt einen schmalen Wrapper um die Windows-Datei Behandlungs-API bereit.|atlfile. h|
|[CAtlFileMapping](../../atl/reference/catlfilemapping-class.md)|Diese Klasse stellt eine Speicher Abbild Datei dar und fügt den [Methoden von "](../../atl/reference/catlfilemappingbase-class.md)" für "" von "" die Methode "" von "" für "".|atlfile. h|
|[CAtlFileMappingBase](../../atl/reference/catlfilemappingbase-class.md)|Diese Klasse stellt eine Speicher Abbild Datei dar.|atlfile. h|
|[Die Kategorie](../../atl/reference/catllist-class.md)|Diese Klasse stellt Methoden zum Erstellen und Verwalten eines Listen Objekts bereit.|atlcoll. h|
|[CAtlMap](../../atl/reference/catlmap-class.md)|Diese Klasse stellt Methoden zum Erstellen und Verwalten eines Map-Objekts bereit.|atlcoll. h|
|[CAtlModule](../../atl/reference/catlmodule-class.md)|Diese Klasse stellt Methoden bereit, die von mehreren ATL-Modul Klassen verwendet werden.|atlbase. h|
|[CAtlModuleT](../../atl/reference/catlmodulet-class.md)|Diese Klasse implementiert ein ATL-Modul.|atlbase. h|
|[CAtlPreviewCtrlImpl](../../atl/reference/catlpreviewctrlimpl-class.md)|Diese Klasse ist eine ATL-Implementierung eines Fensters, das in einem Host Fenster platziert wird, das von der Shell für eine umfangreiche Vorschau bereitgestellt wird.|atlpreviewctrlimpl.h|
|[CAtlServiceModuleT](../../atl/reference/catlservicemodulet-class.md)|Diese Klasse implementiert einen Dienst.|atlbase. h|
|[CAtlTemporaryFile](../../atl/reference/catltemporaryfile-class.md)|Diese Klasse stellt Methoden zum Erstellen und Verwenden einer temporären Datei bereit.|atlfile. h|
|[CAtlTransactionManager](../../atl/reference/catltransactionmanager-class.md)|Diese Klasse stellt einen Wrapper für die Kerneltransaktions-Manager-Funktionen (KTM) bereit.|atltransactionmanager.h|
|[CAtlWinModule](../../atl/reference/catlwinmodule-class.md)|Diese Klasse bietet Unterstützung für ATL-windowingkomponenten.|atlbase. h|
|[CAutoPtr](../../atl/reference/cautoptr-class.md)|Diese Klasse stellt ein intelligentes Zeiger Objekt dar.|atlbase. h|
|[CAutoPtrArray](../../atl/reference/cautoptrarray-class.md)|Diese Klasse stellt Methoden bereit, die beim Erstellen eines Arrays von intelligenten Zeigern hilfreich sind.|atlbase. h|
|[Cautoptrelementtrait](../../atl/reference/cautoptrelementtraits-class.md)|Diese Klasse stellt Methoden, statische Funktionen und Typedefs bereit, die beim Erstellen von Auflistungen von intelligenten Zeigern hilfreich sind.|atlcoll. h|
|[CAutoPtrList](../../atl/reference/cautoptrlist-class.md)|Diese Klasse stellt Methoden bereit, die beim Erstellen einer Liste von intelligenten Zeigern hilfreich sind.|atlcoll. h|
|[CAutoVectorPtr](../../atl/reference/cautovectorptr-class.md)|Diese Klasse stellt ein intelligentes Zeiger Objekt mithilfe von Vector New-und DELETE-Operatoren dar.|atlbase. h|
|[CAutoVectorPtrElementTraits](../../atl/reference/cautovectorptrelementtraits-class.md)|Diese Klasse stellt Methoden, statische Funktionen und Typedefs zum Erstellen von Auflistungen von intelligenten Zeigern mithilfe von Vector New-und DELETE-Operatoren bereit.|atlcoll. h|
|[CAxDialogImpl](../../atl/reference/caxdialogimpl-class.md)|Diese Klasse implementiert ein (modales oder nicht modales) Dialogfeld, das ActiveX-Steuerelemente hostet.|atlwin. h|
|[CAxWindow](../../atl/reference/caxwindow-class.md)|Diese Klasse stellt Methoden zum Bearbeiten eines Fensters bereit, das ein ActiveX-Steuerelement gehostet.|atlwin. h|
|[CAxWindow2T](../../atl/reference/caxwindow2t-class.md)|Diese Klasse stellt Methoden zum Bearbeiten eines Fensters bereit, das ein ActiveX-Steuerelement hostet und auch das Hosten von lizenzierten ActiveX-Steuerelementen unterstützt.|atlwin. h|
|[CBindStatusCallback](../../atl/reference/cbindstatuscallback-class.md)|Diese Klasse implementiert die `IBindStatusCallback` -Schnittstelle.|atlctl. h|
|[CComAggObject](../../atl/reference/ccomaggobject-class.md)|Diese Klasse implementiert [IUnknown](/windows/win32/api/unknwn/nn-unknwn-iunknown) für ein aggregiertes Objekt.|Atlcom. h|
|[CComAllocator](../../atl/reference/ccomallocator-class.md)|Diese Klasse stellt Methoden zum Verwalten von Speicher mithilfe von com-Speicher Routinen bereit.|atlbase. h|
|[CComApartment](../../atl/reference/ccomapartment-class.md)|Diese Klasse bietet Unterstützung für die Verwaltung eines Apartment in einem Modul mit einem Thread im Pool.|atlbase. h|
|[CComAutoCriticalSection](../../atl/reference/ccomautocriticalsection-class.md)|Diese Klasse stellt Methoden zum Abrufen und Freigeben des Besitzes eines kritischen Abschnitts Objekts bereit.|atlcore. h|
|[CComAutoThreadModule](../../atl/reference/ccomautothreadmodule-class.md)|Ab ATL 7,0 `CComAutoThreadModule` ist veraltet: Weitere Informationen finden Sie in den [ATL-Modulen](../../atl/atl-module-classes.md) .|atlbase. h|
|[CComBSTR](../../atl/reference/ccombstr-class.md)|Diese Klasse ist ein Wrapper für bstrins.|atlbase. h|
|[CComCachedTearOffObject](../../atl/reference/ccomcachedtearoffobject-class.md)|Diese Klasse implementiert [IUnknown](/windows/win32/api/unknwn/nn-unknwn-iunknown) für eine abtrennbare Schnittstelle.|Atlcom. h|
|[CComClassFactory](../../atl/reference/ccomclassfactory-class.md)|Diese Klasse implementiert die [IClassFactory](/windows/win32/api/unknwnbase/nn-unknwnbase-iclassfactory) -Schnittstelle.|Atlcom. h|
|[CComClassFactory2](../../atl/reference/ccomclassfactory2-class.md)|Diese Klasse implementiert die [IClassFactory2](/windows/win32/api/ocidl/nn-ocidl-iclassfactory2) -Schnittstelle.|Atlcom. h|
|[CComClassFactoryAutoThread](../../atl/reference/ccomclassfactoryautothread-class.md)|Diese Klasse implementiert die [IClassFactory](/windows/win32/api/unknwnbase/nn-unknwnbase-iclassfactory) -Schnittstelle und ermöglicht das Erstellen von Objekten in mehreren Apartments.|Atlcom. h|
|[CComClassFactorySingleton](../../atl/reference/ccomclassfactorysingleton-class.md)|Diese Klasse wird von [CComClassFactory](../../atl/reference/ccomclassfactory-class.md) abgeleitet und verwendet [ccomobjectglobal](../../atl/reference/ccomobjectglobal-class.md) , um ein einzelnes Objekt zu erstellen.|Atlcom. h|
|[CComCoClass](../../atl/reference/ccomcoclass-class.md)|Diese Klasse stellt Methoden zum Erstellen von Instanzen einer Klasse und zum Abrufen ihrer Eigenschaften bereit.|Atlcom. h|
|[CComCompositeControl](../../atl/reference/ccomcompositecontrol-class.md)|Diese Klasse stellt die Methoden bereit, die zum Implementieren eines zusammengesetzten Steuer Elements erforderlich sind.|atlctl. h|
|[CComContainedObject](../../atl/reference/ccomcontainedobject-class.md)|Diese Klasse implementiert [IUnknown](/windows/win32/api/unknwn/nn-unknwn-iunknown) , indem an die des Besitzer Objekts `IUnknown`delegiert wird.|Atlcom. h|
|[CComControl](../../atl/reference/ccomcontrol-class.md)|Diese Klasse stellt Methoden zum Erstellen und Verwalten von ATL-Steuerelementen bereit.|atlctl. h|
|[CComControlBase](../../atl/reference/ccomcontrolbase-class.md)|Diese Klasse stellt Methoden zum Erstellen und Verwalten von ATL-Steuerelementen bereit.|atlctl. h|
|[CComCriticalSection](../../atl/reference/ccomcriticalsection-class.md)|Diese Klasse stellt Methoden zum Abrufen und Freigeben des Besitzes eines kritischen Abschnitts Objekts bereit.|atlcore. h|
|[CComCritSecLock](../../atl/reference/ccomcritseclock-class.md)|Diese Klasse stellt Methoden zum Sperren und Entsperren eines kritischen Abschnitts Objekts bereit.|atlbase. h|
|[CComCurrency](../../atl/reference/ccomcurrency-class.md)|Diese Klasse verfügt über Methoden und Operatoren zum Erstellen und Verwalten eines Currency-Objekts.|atlcur. h|
|[CComDynamicUnkArray](../../atl/reference/ccomdynamicunkarray-class.md)|Diese Klasse speichert ein Array von `IUnknown` Zeigern.|Atlcom. h|
|[CComEnum](../../atl/reference/ccomenum-class.md)|Diese Klasse definiert ein com-Enumeratorobjekt, das auf einem Array basiert.|Atlcom. h|
|[CComEnumImpl](../../atl/reference/ccomenumimpl-class.md)|Diese Klasse stellt die Implementierung für eine com-Enumeratorschnittstelle bereit, bei der die aufzuzählenden Elemente in einem Array gespeichert werden.|Atlcom. h|
|[CComEnumOnSTL](../../atl/reference/ccomenumonstl-class.md)|Diese Klasse definiert ein com-Enumeratorobjekt, das C++ auf einer Standard Bibliothekssammlung basiert.|Atlcom. h|
|[CComFakeCriticalSection](../../atl/reference/ccomfakecriticalsection-class.md)|Diese Klasse stellt die gleichen Methoden wie [ccomcriticalsection](../../atl/reference/ccomcriticalsection-class.md) bereit, stellt jedoch keinen kritischen Abschnitt bereit.|atlcore. h|
|[CComGITPtr](../../atl/reference/ccomgitptr-class.md)|Diese Klasse stellt Methoden für den Umgang mit Schnittstellen Zeigern und der globalen Schnittstellen Tabelle (git) bereit.|atlbase. h|
|[CComHeap](../../atl/reference/ccomheap-class.md)|Diese Klasse implementiert [IAtlMemMgr](../../atl/reference/iatlmemmgr-class.md) mithilfe der com-Speicher Belegungs Funktionen.|ATLComMem.h|
|[CComHeapPtr](../../atl/reference/ccomheapptr-class.md)|Eine intelligente Zeiger Klasse zum Verwalten von Heap Zeigern.|atlbase. h|
|[CComModule](../../atl/reference/ccommodule-class.md)|Ab ATL 7,0 `CComModule` ist veraltet: Weitere Informationen finden Sie in den [ATL-Modulen](../../atl/atl-module-classes.md) .|atlbase. h|
|[CComMultiThreadModel](../../atl/reference/ccommultithreadmodel-class.md)|Diese Klasse stellt Thread sichere Methoden zum Inkrementieren und Dekrementieren des Werts einer Variablen bereit.|atlbase. h|
|[CComMultiThreadModelNoCS](../../atl/reference/ccommultithreadmodelnocs-class.md)|Diese Klasse stellt Thread sichere Methoden bereit, mit denen der Wert einer Variablen erhöht und dekrementiert werden kann, ohne dass die Funktionalität des kritischen Abschnitts gesperrt ist.|atlbase. h|
|[CComObject](../../atl/reference/ccomobject-class.md)|Diese Klasse implementiert `IUnknown` für ein nicht aggregiertes-Objekt.|Atlcom. h|
|[CComObjectGlobal](../../atl/reference/ccomobjectglobal-class.md)|Diese Klasse verwaltet einen Verweis Zähler für das Modul, das `Base` das Objekt enthält.|Atlcom. h|
|[CComObjectNoLock](../../atl/reference/ccomobjectnolock-class.md)|Diese Klasse implementiert `IUnknown` für ein nicht aggregiertes Objekt, erhöht jedoch nicht die Anzahl der Modul Sperren im Konstruktor.|Atlcom. h|
|[CComObjectRoot](../../atl/reference/ccomobjectroot-class.md)|Diese Typdefinition von [CComObjectRootEx](../../atl/reference/ccomobjectrootex-class.md) ist im Standard Threading Modell des Servers Vorlagen basiert.|Atlcom. h|
|[CComObjectRootEx](../../atl/reference/ccomobjectrootex-class.md)|Diese Klasse stellt Methoden bereit, um die Verwaltung der Objekt Verweis Zählung sowohl für nicht aggregierte als auch für aggregierte Objekte zu behandeln.|Atlcom. h|
|[CComObjectStack](../../atl/reference/ccomobjectstack-class.md)|Diese Klasse erstellt ein temporäres com-Objekt und stellt ihm eine Skelett Implementierung `IUnknown`von bereit.|Atlcom. h|
|[CComPolyObject](../../atl/reference/ccompolyobject-class.md)|Diese Klasse implementiert `IUnknown` für ein aggregiertes oder nicht aggregiertes Objekt.|Atlcom. h|
|[CComPtr](../../atl/reference/ccomptr-class.md)|Eine intelligente Zeiger Klasse zum Verwalten von COM-Schnittstellen Zeigern.|atlcomcli. h|
|[CComPtrBase](../../atl/reference/ccomptrbase-class.md)|Diese Klasse stellt eine Basis für intelligente Zeiger Klassen mithilfe von COM-basierten Speicher Routinen bereit.|atlcomcli. h|
|[CComQIPtr](../../atl/reference/ccomqiptr-class.md)|Eine intelligente Zeiger Klasse zum Verwalten von COM-Schnittstellen Zeigern.|atlcomcli. h|
|[CComQIPtrElementTraits](../../atl/reference/ccomqiptrelementtraits-class.md)|Diese Klasse stellt Methoden, statische Funktionen und Typedefs bereit, die beim Erstellen von Auflistungen von COM-Schnittstellen Zeigern hilfreich sind.|atlcoll. h|
|[CComSafeArray](../../atl/reference/ccomsafearray-class.md)|Diese Klasse ist ein Wrapper für die `SAFEARRAY Data Type` -Struktur.|atlsafe.h|
|[CComSafeArrayBound](../../atl/reference/ccomsafearraybound-class.md)|Diese Klasse ist ein Wrapper für eine `SAFEARRAYBOUND` -Struktur.|atlsafe.h|
|[CComSimpleThreadAllocator](../../atl/reference/ccomsimplethreadallocator-class.md)|Diese Klasse verwaltet die Thread Auswahl für die [CComAutoThreadModule](../../atl/reference/ccomautothreadmodule-class.md)-Klasse.|atlbase. h|
|[CComSingleThreadModel](../../atl/reference/ccomsinglethreadmodel-class.md)|Diese Klasse stellt Methoden zum Inkrementieren und Dekrementieren des Werts einer Variablen bereit.|atlbase. h|
|[CComTearOffObject](../../atl/reference/ccomtearoffobject-class.md)|Diese Klasse implementiert eine deaktivierte Schnittstelle.|Atlcom. h|
|[CComUnkArray](../../atl/reference/ccomunkarray-class.md)|Diese Klasse speichert `IUnknown` Zeiger und ist so konzipiert, dass Sie als Parameter für die [IConnectionPointImpl](../../atl/reference/iconnectionpointimpl-class.md) -Vorlagen Klasse verwendet wird.|Atlcom. h|
|[CComVariant](../../atl/reference/ccomvariant-class.md)|Diese Klasse umschließt den Variant-Typ und stellt einen Member bereit, der den Typ der gespeicherten Daten angibt.|atlcomcli. h|
|[CContainedWindowT](../../atl/reference/ccontainedwindowt-class.md)|Diese Klasse implementiert ein Fenster, das in einem anderen-Objekt enthalten ist.|atlwin. h|
|[CCRTAllocator](../../atl/reference/ccrtallocator-class.md)|Diese Klasse stellt Methoden zum Verwalten von Speicher mithilfe von CRT-Speicher Routinen bereit.|atlcore. h|
|[CCRTHeap](../../atl/reference/ccrtheap-class.md)|Diese Klasse implementiert [IAtlMemMgr](../../atl/reference/iatlmemmgr-class.md) mithilfe der CRT-Heap Funktionen.|atlmem. h|
|[CDacl](../../atl/reference/cdacl-class.md)|Diese Klasse ist ein Wrapper für eine DACL-Struktur (freigegebene Zugriffs Steuerungs Liste).|ATLSecurity. h|
|[CDebugReportHook-Klasse](../../atl/reference/cdebugreporthook-class.md)|Verwenden Sie diese Klasse, um Debugberichte an einen Named Pipe zu senden.|atlutil. h|
|[CDefaultCharTraits](../../atl/reference/cdefaultchartraits-class.md)|Diese Klasse stellt zwei statische Funktionen zum Umwandeln von Zeichen zwischen Groß-und Kleinbuchstaben bereit.|atlcoll. h|
|[CDefaultCompareTraits](../../atl/reference/cdefaultcomparetraits-class.md)|Diese Klasse stellt standardmäßige Element Vergleichsfunktionen bereit.|atlcoll. h|
|[CDefaultElementTraits](../../atl/reference/cdefaultelementtraits-class.md)|Diese Klasse stellt Standardmethoden und-Funktionen für eine Auflistungs Klasse bereit.|atlcoll. h|
|[CDefaultHashTraits](../../atl/reference/cdefaulthashtraits-class.md)|Diese Klasse stellt eine statische Funktion zum Berechnen von Hash Werten bereit.|atlcoll. h|
|[CDialogImpl](../../atl/reference/cdialogimpl-class.md)|Diese Klasse stellt Methoden zum Erstellen eines modalen oder nicht modalen Dialog Felds bereit.|atlwin. h|
|[CDynamicChain](../../atl/reference/cdynamicchain-class.md)|Diese Klasse stellt Methoden bereit, die die dynamische Verkettung von Meldungs Zuordnungen unterstützen.|atlwin. h|
|[Celementcharakteristika](../../atl/reference/celementtraits-class.md)|Diese Klasse wird von Auflistungs Klassen verwendet, um Methoden und Funktionen zum Verschieben, kopieren, vergleichen und hashingvorgängen bereitzustellen.|atlcoll. h|
|[CElementTraitsBase](../../atl/reference/celementtraitsbase-class.md)|Diese Klasse stellt standardmäßige Kopier-und Verschiebungs Methoden für eine Auflistungs Klasse bereit.|atlcoll. h|
|[CFirePropNotifyEvent](../../atl/reference/cfirepropnotifyevent-class.md)|Diese Klasse stellt Methoden zum Benachrichtigen der Senke des Containers bezüglich Änderungen an Steuerelement Eigenschaften bereit.|atlctl. h|
|[CGlobalHeap](../../atl/reference/cglobalheap-class.md)|Diese Klasse implementiert [IAtlMemMgr](../../atl/reference/iatlmemmgr-class.md) mithilfe der globalen Win32-Heap Funktionen.|atlmem. h|
|[CHandle](../../atl/reference/chandle-class.md)|Diese Klasse stellt Methoden zum Erstellen und Verwenden eines Handle-Objekts bereit.|atlbase. h|
|[CHeapPtr](../../atl/reference/cheapptr-class.md)|Eine intelligente Zeiger Klasse zum Verwalten von Heap Zeigern.|atlcore. h|
|[CHeapPtrBase](../../atl/reference/cheapptrbase-class.md)|Diese Klasse bildet die Grundlage für mehrere Smart Heap-Zeiger Klassen.|atlcore. h|
|[CHeapPtrElementTraits-Klasse](../../atl/reference/cheapptrelementtraits-class.md)|Diese Klasse stellt Methoden, statische Funktionen und Typedefs bereit, die beim Erstellen von Auflistungen von Heap Zeigern hilfreich sind.|atlcoll. h|
|[CHeapPtrList](../../atl/reference/cheapptrlist-class.md)|Diese Klasse stellt Methoden bereit, die beim Erstellen einer Liste von Heap Zeigern hilfreich sind.|atlcoll. h|
|[CImage](../../atl-mfc-shared/reference/cimage-class.md)|Bietet erweiterte Unterstützung für Bitmap, einschließlich der Möglichkeit, Bilder in JPEG-, GIF-, BMP-und Portable Network Graphics-Formaten (PNG) zu laden und zu speichern.|atlimage. h|
|[CInterfaceArray](../../atl/reference/cinterfacearray-class.md)|Diese Klasse stellt Methoden bereit, die beim Erstellen eines Arrays von COM-Schnittstellen Zeigern hilfreich sind.|atlcoll. h|
|[CInterfaceList](../../atl/reference/cinterfacelist-class.md)|Diese Klasse stellt Methoden bereit, die beim Erstellen einer Liste von COM-Schnittstellen Zeigern hilfreich sind.|atlcoll. h|
|[CLocalHeap](../../atl/reference/clocalheap-class.md)|Diese Klasse implementiert [IAtlMemMgr](../../atl/reference/iatlmemmgr-class.md) mithilfe der Win32-Funktionen für den lokalen Heap.|atlmem. h|
|[CMessageMap](../../atl/reference/cmessagemap-class.md)|Diese Klasse ermöglicht den Zugriff auf die Meldungs Zuordnungen eines Objekts durch ein anderes Objekt.|atlwin. h|
|[CNonStatelessWorker-Klasse](../../atl/reference/cnonstatelessworker-class.md)|Empfängt Anforderungen von einem Thread Pool und übergibt sie an ein Worker-Objekt, das bei jeder Anforderung erstellt und zerstört wird.|atlutil. h|
|[CNoWorkerThread-Klasse](../../atl/reference/cnoworkerthread-class.md)|Verwenden Sie diese Klasse als Argument für die `MonitorClass` Vorlagen Parameter-Cache Klassen, wenn Sie die dynamische Cache Wartung deaktivieren möchten.|atlutil. h|
|[CPathT-Klasse](../../atl/reference/cpatht-class.md)|Diese Klasse stellt einen Pfad dar.|atlpath. h|
|[CPrimitiveElementTraits](../../atl/reference/cprimitiveelementtraits-class.md)|Diese Klasse stellt Standardmethoden und-Funktionen für eine Auflistungs Klasse bereit, die aus primitiven Datentypen besteht.|atlcoll. h|
|[CPrivateObjectSecurityDesc](../../atl/reference/cprivateobjectsecuritydesc-class.md)|Diese Klasse stellt ein Sicherheits beschreibungerobjekt für private Objekte dar.|ATLSecurity. h|
|[CRBMap](../../atl/reference/crbmap-class.md)|Diese Klasse stellt eine Mapping-Struktur dar, die eine rotschwarze binäre Struktur verwendet.|atlcoll. h|
|[CRBMultiMap](../../atl/reference/crbmultimap-class.md)|Diese Klasse stellt eine Zuordnungsstruktur dar, die es dem einzelnen Schlüssel ermöglicht, mit einer roten und schwarzen binär Struktur mehr als einem Wert zugeordnet zu werden.|atlcoll. h|
|[Crbtree](../../atl/reference/crbtree-class.md)|Diese Klasse stellt Methoden zum Erstellen und Verwenden eines roten schwarzen Baums bereit.|atlcoll. h|
|[CRegKey](../../atl/reference/cregkey-class.md)|Diese Klasse stellt Methoden zum Bearbeiten von Einträgen in der Systemregistrierung bereit.|atlbase. h|
|[CRTThreadTraits](../../atl/reference/crtthreadtraits-class.md)|Diese Klasse stellt die Erstellungs Funktion für einen CRT-Thread bereit. Verwenden Sie diese Klasse, wenn der Thread CRT-Funktionen verwendet.|atlbase. h|
|[CSacl](../../atl/reference/csacl-class.md)|Diese Klasse ist ein Wrapper für eine SACL-Struktur (Systemzugriffssteuerungsliste).|ATLSecurity. h|
|[CSecurityAttributes](../../atl/reference/csecurityattributes-class.md)|Diese Klasse ist ein schlanker Wrapper für die `SECURITY_ATTRIBUTES` -Struktur.|ATLSecurity. h|
|[CSecurityDesc](../../atl/reference/csecuritydesc-class.md)|Diese Klasse ist ein Wrapper für die `SECURITY_DESCRIPTOR` -Struktur.|ATLSecurity. h|
|[CSid](../../atl/reference/csid-class.md)|Diese Klasse ist ein Wrapper für eine `SID` (sicherheitsbezeichnerstruktur).|ATLSecurity. h|
|[CSimpleArray](../../atl/reference/csimplearray-class.md)|Diese Klasse stellt Methoden zum Verwalten eines einfachen Arrays bereit.|atlsimpcoll. h|
|[CSimpleArrayEqualHelper](../../atl/reference/csimplearrayequalhelper-class.md)|Diese Klasse ist ein Hilfsprogramm für die [CSimpleArray](../../atl/reference/csimplearray-class.md) -Klasse.|atlsimpcoll. h|
|[CSimpleArrayEqualHelperFalse](../../atl/reference/csimplearrayequalhelperfalse-class.md)|Diese Klasse ist ein Hilfsprogramm für die [CSimpleArray](../../atl/reference/csimplearray-class.md) -Klasse.|atlsimpcoll. h|
|[CSimpleDialog](../../atl/reference/csimpledialog-class.md)|Diese Klasse implementiert ein einfaches modales Dialogfeld.|atlwin. h|
|[CSimpleMap](../../atl/reference/csimplemap-class.md)|Diese Klasse bietet Unterstützung für ein einfaches Mapping-Array.|atlsimpcoll. h|
|[CSimpleMapEqualHelper](../../atl/reference/csimplemapequalhelper-class.md)|Diese Klasse ist ein Hilfsprogramm für die [CSimpleMap](../../atl/reference/csimplemap-class.md) -Klasse.|atlsimpcoll. h|
|[CSimpleMapEqualHelperFalse](../../atl/reference/csimplemapequalhelperfalse-class.md)|Diese Klasse ist ein Hilfsprogramm für die [CSimpleMap](../../atl/reference/csimplemap-class.md) -Klasse.|atlsimpcoll. h|
|[CSnapInItemImpl](../../atl/reference/csnapinitemimpl-class.md)|Diese Klasse stellt Methoden zum Implementieren eines Snap-in-Knoten Objekts bereit.|atlsnap. h|
|[CSnapInPropertyPageImpl](../../atl/reference/csnapinpropertypageimpl-class.md)|Diese Klasse stellt Methoden zum Implementieren eines Snap-in-Eigenschaften Seiten Objekts bereit.|atlsnap. h|
|[CStockPropImpl](../../atl/reference/cstockpropimpl-class.md)|Diese Klasse stellt Methoden zum unterstützen von Aktien Eigenschafts Werten bereit.|atlctl. h|
|[Cstringelementmerkmalen](../../atl/reference/cstringelementtraits-class.md)|Diese Klasse bietet statische Funktionen, die von Auflistungs Klassen `CString` verwendet werden, die-Objekte|cstringt.h|
|[CStringElementTraitsI](../../atl/reference/cstringelementtraitsi-class.md)|Diese Klasse stellt statische Funktionen für Zeichen folgen bereit, die in Auflistungs Klassen Objekten gespeichert sind. Sie ähnelt [cstringelementmerkmalen](../../atl/reference/cstringelementtraits-class.md), führt jedoch Vergleiche ohne Berücksichtigung der Groß-und Kleinschreibung durch.|atlcoll. h|
|[CStringRefElementTraits](../../atl/reference/cstringrefelementtraits-class.md)|Diese Klasse stellt statische Funktionen für Zeichen folgen bereit, die in Auflistungs Klassen Objekten gespeichert sind. Die Zeichen folgen Objekte werden als Verweise behandelt.|atlcoll. h|
|[CThreadPool-Klasse](../../atl/reference/cthreadpool-class.md)|Diese Klasse stellt einen Pool von Arbeitsthreads bereit, die eine Warteschlange von Arbeits Elementen verarbeiten.|atlutil. h|
|[CTokenGroups](../../atl/reference/ctokengroups-class.md)|Diese Klasse ist ein Wrapper für die `TOKEN_GROUPS` -Struktur.|ATLSecurity. h|
|[Ctokenprivilegien](../../atl/reference/ctokenprivileges-class.md)|Diese Klasse ist ein Wrapper für die `TOKEN_PRIVILEGES` -Struktur.|ATLSecurity. h|
|[CUrl-Klasse](../../atl/reference/curl-class.md)|Diese Klasse stellt eine URL dar. Sie ermöglicht es Ihnen, jedes Element der URL unabhängig von den anderen zu bearbeiten, unabhängig davon, ob Sie eine vorhandene URL-Zeichenfolge oder eine Zeichenfolge von Grund auf erstellen.|atlutil. h|
|[CW2AEX](../../atl/reference/cw2aex-class.md)|Diese Klasse wird von den Zeichen folgen Konvertierungs Makros CT2AEX, CW2TEX, CW2CTEX und CT2CAEX sowie von typedef CW2A verwendet.|atlrev. h|
|[CW2CWEX](../../atl/reference/cw2cwex-class.md)|Diese Klasse wird von den Zeichen folgen Konvertierungs Makros CW2CTEX und CT2CWEX sowie von typedef CW2CW verwendet.|atlrev. h|
|[CW2WEX](../../atl/reference/cw2wex-class.md)|Diese Klasse wird von den Zeichen folgen Konvertierungs Makros CW2TEX und CT2WEX sowie von typedef CW2W verwendet.|atlrev. h|
|[CWin32Heap](../../atl/reference/cwin32heap-class.md)|Diese Klasse implementiert [IAtlMemMgr](../../atl/reference/iatlmemmgr-class.md) mithilfe der Win32-Heap Zuordnungs Funktionen.|atlmem. h|
|[CWindow](../../atl/reference/cwindow-class.md)|Diese Klasse stellt Methoden zum Bearbeiten eines Fensters bereit.|atlwin. h|
|[CWindowImpl](../../atl/reference/cwindowimpl-class.md)|Diese Klasse stellt Methoden zum Erstellen oder Unterklassen eines Fensters bereit.|atlwin. h|
|[CWinTraits](../../atl/reference/cwintraits-class.md)|Diese Klasse stellt eine Methode zum standardialisieren der Stile bereit, die beim Erstellen eines Fenster Objekts verwendet werden.|atlwin. h|
|[CWinTraitsOR](../../atl/reference/cwintraitsor-class.md)|Diese Klasse stellt eine Methode zum standardialisieren der Stile bereit, die beim Erstellen eines Fenster Objekts verwendet werden.|atlwin. h|
|[CWndClassInfo](../../atl/reference/cwndclassinfo-class.md)|Diese Klasse stellt Methoden zum Registrieren von Informationen für eine Fenster Klasse bereit.|atlwin. h|
|[CWorkerThread-Klasse](../../atl/reference/cworkerthread-class.md)|Diese Klasse erstellt einen Arbeits Thread oder verwendet einen vorhandenen Thread, wartet auf ein oder mehrere Kernel Objekt Handles und führt eine angegebene Client Funktion aus, wenn eines der Handles signalisiert wird.|atlutil. h|
|[IAtlAutoThreadModule](../../atl/reference/iatlautothreadmodule-class.md)|Diese Klasse stellt eine Schnittstelle zu `CreateInstance` einer Methode dar.|atlbase. h|
|[IAtlMemMgr](../../atl/reference/iatlmemmgr-class.md)|Diese Klasse stellt die Schnittstelle zu einem Speicher-Manager dar.|atlmem. h|
|[IAxWinAmbientDispatch](../../atl/reference/iaxwinambientdispatch-interface.md)|Diese Schnittstelle stellt Methoden zum Angeben von Merkmalen für das gehostete Steuerelement oder den Container bereit.|atlbase. h, atliface. h|
|[IAxWinAmbientDispatchEx](../../atl/reference/iaxwinambientdispatchex-interface.md)|Diese Schnittstelle implementiert zusätzliche Ambient-Eigenschaften für ein gehosteter-Steuerelement.|atlbase. h, atliface. h|
|[IAxWinHostWindow](../../atl/reference/iaxwinhostwindow-interface.md)|Diese Schnittstelle stellt Methoden zum Bearbeiten eines Steuer Elements und seines Host Objekts bereit.|atlbase. h, atliface. h|
|[IAxWinHostWindowLic](../../atl/reference/iaxwinhostwindowlic-interface.md)|Diese Schnittstelle stellt Methoden zum Bearbeiten eines lizenzierten Steuer Elements und seines Host Objekts bereit.|atlbase. h, atliface. h|
|[ICollectionOnSTLImpl](../../atl/reference/icollectiononstlimpl-class.md)|Diese Klasse stellt Methoden bereit, die von Auflistungs Klassen verwendet werden.|Atlcom. h|
|[IConnectionPointContainerImpl](../../atl/reference/iconnectionpointcontainerimpl-class.md)|Diese Klasse implementiert einen Verbindungspunkt Container zum Verwalten einer Auflistung von [IConnectionPointImpl](../../atl/reference/iconnectionpointimpl-class.md) -Objekten.|Atlcom. h|
|[IConnectionPointImpl](../../atl/reference/iconnectionpointimpl-class.md)|Diese Klasse implementiert einen Verbindungspunkt.|Atlcom. h|
|[IDataObjectImpl](../../atl/reference/idataobjectimpl-class.md)|Diese Klasse stellt Methoden zum unterstützen von Uniform Data Transfer und zum Verwalten von Verbindungen bereit.|atlctl. h|
|[IDispatchImpl](../../atl/reference/idispatchimpl-class.md)|Diese Klasse stellt eine Standard Implementierung für den `IDispatch` -Teil einer Dual-Schnittstelle bereit.|Atlcom. h|
|[IDispEventImpl](../../atl/reference/idispeventimpl-class.md)|Diese Klasse stellt Implementierungen der `IDispatch` -Methoden bereit.|Atlcom. h|
|[IDispEventSimpleImpl](../../atl/reference/idispeventsimpleimpl-class.md)|Diese Klasse stellt Implementierungen der `IDispatch` -Methoden bereit, ohne Typinformationen aus einer Typbibliothek zu erhalten.|Atlcom. h|
|[IDocHostUIHandlerDispatch](../../atl/reference/idochostuihandlerdispatch-interface.md)|Eine Schnittstelle zum Microsoft HTML-Modul für die-und-Rendering-Engine.|atlbase. h, atliface. h|
|[IEnumOnSTLImpl](../../atl/reference/ienumonstlimpl-class.md)|Diese Klasse definiert eine Enumeratorschnittstelle, die auf C++ einer Standard Bibliotheks Auflistung basiert.|Atlcom. h|
|[IObjectSafetyImpl](../../atl/reference/iobjectsafetyimpl-class.md)|Diese Klasse stellt eine Standard Implementierung der- `IObjectSafety` Schnittstelle bereit, die es einem Client ermöglicht, die Sicherheitsebenen eines Objekts abzurufen und festzulegen.|atlctl. h|
|[IObjectWithSiteImpl](../../atl/reference/iobjectwithsiteimpl-class.md)|Diese Klasse stellt Methoden bereit, mit denen ein Objekt mit seiner Website kommunizieren kann.|Atlcom. h|
|[IOleControlImpl](../../atl/reference/iolecontrolimpl-class.md)|Diese Klasse stellt eine Standard Implementierung der `IOleControl` -Schnittstelle bereit und implementiert. `IUnknown`|atlctl. h|
|[IOleInPlaceActiveObjectImpl](../../atl/reference/ioleinplaceactiveobjectimpl-class.md)|Diese Klasse stellt Methoden zur Unterstützung der Kommunikation zwischen einer direkten Steuerung und deren Container bereit.|atlctl. h|
|[IOleInPlaceObjectWindowlessImpl](../../atl/reference/ioleinplaceobjectwindowlessimpl-class.md)|Diese Klasse implementiert `IUnknown` und stellt Methoden bereit, die einem fensterlosen Steuerelement ermöglichen, Fenster Meldungen zu empfangen und an Drag & Drop-Vorgängen teilzunehmen.|atlctl. h|
|[IOleObjectImpl](../../atl/reference/ioleobjectimpl-class.md)|Diese Klasse implementiert `IUnknown` und ist die Prinzipal Schnittstelle, über die ein Container mit einem-Steuerelement kommuniziert.|atlctl. h|
|[IPerPropertyBrowsingImpl](../../atl/reference/iperpropertybrowsingimpl-class.md)|Diese Klasse implementiert `IUnknown` und ermöglicht einem Client den Zugriff auf die Informationen auf den Eigenschaften Seiten eines Objekts.|atlctl. h|
|[IPersistPropertyBagImpl](../../atl/reference/ipersistpropertybagimpl-class.md)|Diese Klasse implementiert `IUnknown` und ermöglicht einem Objekt, seine Eigenschaften in einem vom Client bereitgestellten Eigenschaften Behälter zu speichern.|Atlcom. h|
|[IPersistStorageImpl](../../atl/reference/ipersiststorageimpl-class.md)|Diese Klasse implementiert die [IPersistStorage](/windows/win32/api/objidl/nn-objidl-ipersiststorage) -Schnittstelle.|Atlcom. h|
|[IPersistStreamInitImpl](../../atl/reference/ipersiststreaminitimpl-class.md)|Diese Klasse implementiert `IUnknown` und stellt eine Standard Implementierung der [IPersistStreamInit](/windows/win32/api/ocidl/nn-ocidl-ipersiststreaminit) -Schnittstelle bereit.|Atlcom. h|
|[IPointerInactiveImpl](../../atl/reference/ipointerinactiveimpl-class.md)|Diese Klasse implementiert `IUnknown` und die [ipointerininaktiven](/windows/win32/api/ocidl/nn-ocidl-ipointerinactive) Schnittstellen Methoden.|atlctl. h|
|[IPropertyNotifySinkCP](../../atl/reference/ipropertynotifysinkcp-class.md)|Diese Klasse macht die [IPropertyNotifySink](/windows/win32/api/ocidl/nn-ocidl-ipropertynotifysink) -Schnittstelle als ausgehende Schnittstelle für ein Verbindungs fähiges Objekt verfügbar.|atlctl. h|
|[IPropertyPage2Impl](../../atl/reference/ipropertypage2impl-class.md)|Diese Klasse implementiert `IUnknown` und erbt die Standard Implementierung von [IPropertyPageImpl](../../atl/reference/ipropertypageimpl-class.md).|atlctl. h|
|[IPropertyPageImpl](../../atl/reference/ipropertypageimpl-class.md)|Diese Klasse implementiert `IUnknown` und stellt eine Standard Implementierung der [IPropertyPage](/windows/win32/api/ocidl/nn-ocidl-ipropertypage) -Schnittstelle bereit.|atlctl. h|
|[IProvideClassInfo2Impl](../../atl/reference/iprovideclassinfo2impl-class.md)|Diese Klasse stellt eine Standard Implementierung der [IProvideClassInfo](/windows/win32/api/ocidl/nn-ocidl-iprovideclassinfo) -Methode und der [IProvideClassInfo2](/windows/win32/api/ocidl/nn-ocidl-iprovideclassinfo2) -Methode bereit.|Atlcom. h|
|[IQuickActivateImpl](../../atl/reference/iquickactivateimpl-class.md)|Diese Klasse kombiniert die Initialisierung von Container Steuerelementen zu einem einzelnen-Befehl.|atlctl. h|
|[IRunnableObjectImpl](../../atl/reference/irunnableobjectimpl-class.md)|Diese Klasse implementiert `IUnknown` und stellt eine Standard Implementierung der [ununnableobject](/windows/win32/api/objidl/nn-objidl-irunnableobject) -Schnittstelle bereit.|atlctl. h|
|[IServiceProviderImpl](../../atl/reference/iserviceproviderimpl-class.md)|Diese Klasse stellt eine Standard Implementierung der `IServiceProvider` -Schnittstelle bereit.|Atlcom. h|
|[ISpecifyPropertyPagesImpl](../../atl/reference/ispecifypropertypagesimpl-class.md)|Diese Klasse implementiert `IUnknown` und stellt eine Standard Implementierung der [ISpecifyPropertyPages](/windows/win32/api/ocidl/nn-ocidl-ispecifypropertypages) -Schnittstelle bereit.|Atlcom. h|
|[ISupportErrorInfoImpl](../../atl/reference/isupporterrorinfoimpl-class.md)|Diese Klasse stellt eine Standard Implementierung der `ISupportErrorInfo Interface` -Schnittstelle bereit und kann verwendet werden, wenn nur eine einzige Schnittstelle Fehler für ein Objekt generiert.|Atlcom. h|
|[IThreadPoolConfig-Schnittstelle](../../atl/reference/ithreadpoolconfig-interface.md)|Diese Schnittstelle stellt Methoden zum Konfigurieren eines Thread Pools bereit.|atlutil. h|
|[IViewObjectExImpl](../../atl/reference/iviewobjecteximpl-class.md)|Diese Klasse implementiert `IUnknown` und stellt Standard Implementierungen der Schnittstellen [IViewObject](/windows/win32/api/oleidl/nn-oleidl-iviewobject), [IViewObject2](/windows/win32/api/oleidl/nn-oleidl-iviewobject2)und [IViewObjectEx](/windows/win32/api/ocidl/nn-ocidl-iviewobjectex) bereit.|atlctl. h|
|[IWorkerThreadClient-Schnittstelle](../../atl/reference/iworkerthreadclient-interface.md)|`IWorkerThreadClient`ist die Schnittstelle, die von Clients der [CWorkerThread](../../atl/reference/cworkerthread-class.md) -Klasse implementiert wird.|atlutil. h|
|[_U_MENUorID](../../atl/reference/u-menuorid-class.md)|Diese Klasse stellt Wrapper für `CreateWindow` und `CreateWindowEx`bereit.|atlwin. h|
|[_U_RECT](../../atl/reference/u-rect-class.md)|Diese Argument Adapter Klasse ermöglicht `RECT` die Übergabe von Zeigern oder verweisen an eine Funktion, die in Bezug auf Zeiger implementiert ist.|atlwin. h|
|[_U_STRINGorID](../../atl/reference/u-stringorid-class.md)|Diese Argument Adapter Klasse ermöglicht das Übergeben von Ressourcennamen (lpctstrans) oder Ressourcen-IDs (uint) an eine Funktion, ohne dass der Aufrufer die ID mithilfe des makeintresource-Makros in eine Zeichenfolge konvertieren muss.|atlwin. h|
|[Win32ThreadTraits](../../atl/reference/win32threadtraits-class.md)|Diese Klasse stellt die Erstellungs Funktion für einen Windows-Thread bereit. Verwenden Sie diese Klasse, wenn der Thread keine CRT-Funktionen verwendet.|atlbase. h|

## <a name="see-also"></a>Siehe auch

[ATL-COM-Desktop-Komponenten](../../atl/atl-com-desktop-components.md)<br/>
[Funktionen](../../atl/reference/atl-functions.md)<br/>
[Globale Variablen](../../atl/reference/atl-global-variables.md)<br/>
[Typedefs](../../atl/reference/atl-typedefs.md)<br/>
[Klassen Übersicht](../../atl/atl-class-overview.md)
