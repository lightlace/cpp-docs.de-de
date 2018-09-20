---
title: Makros und Funktionen für die Verwaltung von DLLs | Microsoft-Dokumentation
ms.custom: ''
ms.date: 04/03/2017
ms.technology:
- cpp-mfc
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- module macros in MFC
ms.assetid: 303f4161-cb5e-4099-81ad-acdb11aa60fb
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 426e23aa935cd0b0add664c1eeb3885181cb4e6b
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/19/2018
ms.locfileid: "46383752"
---
# <a name="macros-and-functions-for-managing-dlls"></a>Makros und Funktionen für die Verwaltung von DLLs

|||
|-|-|
|[AFX_EXT_CLASS](#afx_ext_class)]|Klassen, die exportiert.|
|[AFX_MANAGE_STATE](#afx_manage_state)|Schützen Sie eine exportierte Funktion in einer DLL.|
|[AfxOleInitModule](#afxoleinitmodule)|Bietet Unterstützung von OLE aus einer regulären MFC-DLL, die dynamisch mit MFC verknüpft wird.|
|[AfxNetInitModule](#afxnetinitmodule)|Bietet MFC-Sockets aus einer regulären MFC-DLL, die dynamisch mit MFC verknüpft wird.|
|[AfxGetAmbientActCtx](#afxgetambientactctx)|Ruft den aktuellen Status des pro-Module-Status-Flags ab.|
|[AfxGetStaticModuleState](#afxgetstaticmodulestate)|Legt den Zustand vor der Initialisierung bzw. den vorherigen Zustand nach der Bereinigung wiederherstellen.|
|[AfxInitExtensionModule]()#afxinitextensionmodule|Initialisiert die DLL an.|
|[AfxSetAmbientActCtx](#afxsetambientactctx)|Legen Sie das pro-Module-Status-Flag, das von MFC die WinSxS-Verhalten wirkt sich auf.|
|[AfxTermExtensionModule]()#afxtermextensionmodule)|Ermöglicht es MFC so bereinigen Sie die MFC-Erweiterungs-DLL wird jeder Prozess von der DLL getrennt.|


## <a name="afx_ext_class"></a>  AFX_EXT_CLASS

[MFC-Erweiterungs-DLLs](../../build/extension-dlls.md) verwenden Sie das AFX_EXT_CLASS zum Exportieren von Klassen, die ausführbaren Dateien, die mit der MFC-Erweiterungs-DLL verknüpft wird das Makro verwenden, um Klassen zu importieren.

### <a name="remarks"></a>Hinweise

Mit dem AFX_EXT_CLASS-Makro können der gleiche Header-Dateien verwendet, um die MFC-Erweiterungs-DLL erstellen mit ausführbaren Dateien verwendet werden, die mit der DLL verknüpft.

Fügen Sie in der Headerdatei für die DLL die AFX_EXT_CLASS-Schlüsselwort zur Deklaration der Klasse wie folgt:

```cpp
class AFX_EXT_CLASS CMyClass : public CDocument
{
// <body of class>
};
```

Weitere Informationen finden Sie unter [exportieren und Importieren mithilfe von AFX_EXT_CLASS](../../build/exporting-and-importing-using-afx-ext-class.md).

### <a name="requirements"></a>Anforderungen

Header: **Afxv_** dll.h

## <a name="afx_manage_state"></a>  AFX_MANAGE_STATE

Rufen Sie dieses Makro, um eine exportierte Funktion in einer DLL zu schützen.

### <a name="syntax"></a>Syntax

```
AFX_MANAGE_STATE(AFX_MODULE_STATE* pModuleState )
```
### <a name="parameters"></a>Parameter

*pModuleState*<br/>
Ein Zeiger auf ein `AFX_MODULE_STATE` Struktur.

### <a name="remarks"></a>Hinweise

Wenn dieses Makro aufgerufen wird, *pModuleState* ist der effektive Modulstatus für den Rest der unmittelbaren enthält Bereich. Beim Verlassen des Gültigkeitsbereichs, wird der vorherige Modulstatus der effektiven automatisch wiederhergestellt werden.
Die `AFX_MODULE_STATE` Struktur enthält die globale Daten für das Modul, d. h. der Teil der Modulstatus, die mithilfe von Push übertragen oder per pop ausgelesen wird.
Standardmäßig verwendet MFC Ressourcenhandle von der hauptanwendung beim Laden der Ressourcenvorlage an. Wenn Sie eine exportierte Funktion in einer DLL, z. B. ein verfügen, die startet ein Dialogfeld, in der DLL wird mit dieser Vorlage tatsächlich in das DLL-Modul gespeichert. Sie müssen den Zustand für das richtige Handle verwendet werden zu wechseln. Dazu können Sie den folgenden Code am Anfang der Funktion hinzufügen:
```cpp
AFX_MANAGE_STATE(AfxGetStaticModuleState( ));

```
Dies tauscht den aktuellen Modulstatus mit dem Status von zurückgegebenen [AfxGetStaticModuleState](#afxgetstaticmodulestate) bis zum Ende des aktuellen Gültigkeitsbereichs.
Weitere Informationen zu Modulzustände und MFC, finden Sie unter "Verwalten der Statusdaten von MFC-Modulen" in [Erstellen neuer Dokumente, Windows und Ansichten](../creating-new-documents-windows-and-views.md) und [technischen Hinweis 58](../tn058-mfc-module-state-implementation.md).
> [!NOTE]
>  Wenn MFC einen Aktivierungskontext für eine Assembly erstellt, verwendet es [AfxWinInit](#afxwininit) den Kontext erstellt und `AFX_MANAGE_STATE` aktivieren und deaktivieren. Beachten Sie außerdem, `AFX_MANAGE_STATE` für die statischen MFC-Bibliotheken sowie MFC-DLLs aktiviert ist, damit MFC-Code in der richtigen Aktivierungskontext ausgewählt, die von der DLL für die Benutzer ausführen kann. Weitere Informationen finden Sie unter [Unterstützung für Aktivierungskontexte im MFC-Modulstatus](../support-for-activation-contexts-in-the-mfc-module-state.md).
### <a name="requirements"></a>Anforderungen

**Header:** afxstat_.h

### <a name="see-also"></a>Siehe auch

[AfxGetStaticModuleState](#afxgetstaticmodulestate)

## <a name="a-nameafxoleinitmodulea-afxoleinitmodule"></a><a name="afxoleinitmodule"><a/> AfxOleInitModule

Für OLE-Unterstützung aus einer regulären MFC-DLL, die dynamisch mit MFC verknüpft wird, rufen Sie diese Funktion in Ihre regulären MFC DLL des `CWinApp::InitInstance` Funktion, die die MFC-OLE-DLL zu initialisieren.

### <a name="syntax"></a>Syntax

```
void AFXAPI AfxOleInitModule( );
```

### <a name="remarks"></a>Hinweise

Der MFC-OLE-DLL ist eine MFC-Erweiterungs-DLL. in der Reihenfolge für eine MFC-Erweiterungs-DLL in wired erhalten eine `CDynLinkLibrary` Kette, müssen sie erstellen eine `CDynLinkLibrary` Objekt im Kontext von jedem Modul, die sie verwenden möchten. `AfxOleInitModule` erstellt die `CDynLinkLibrary` Objekts in Ihre regulären MFC DLL Kontext, sodass es in wired Ruft die `CDynLinkLibrary` Objekt Kette von der regulären MFC-DLL.

Wenn Sie ein OLE-Steuerelement erstellen und verwenden `COleControlModule`, rufen Sie nicht `AfxOleInitModule` da die `InitInstance` Memberfunktion `COleControlModule` Aufrufe `AfxOleInitModule`.

### <a name="requirements"></a>Anforderungen

**Header**: \<afxdll_.h >

### <a name="see-also"></a>Siehe auch

[Makros und globale Variablen](mfc-macros-and-globals.md)<br/>
[AfxMessageBox](cstring-formatting-and-message-box-display.md#afxmessagebox)

## <a name="afxnetinitmodule"></a>  AfxNetInitModule

Für MFC-Sockets aus einer regulären MFC-DLL, die dynamisch mit MFC verknüpft wird unterstützen, fügen Sie einen Aufruf dieser Funktion in Ihre regulären MFC DLL des `CWinApp::InitInstance` Funktion, die die MFC-Sockets-DLL zu initialisieren.

### <a name="syntax"></a>Syntax

```
void AFXAPI AfxNetInitModule( );
```

### <a name="remarks"></a>Hinweise

Die MFC-Sockets-DLL ist eine MFC-Erweiterungs-DLL. in der Reihenfolge für eine MFC-Erweiterungs-DLL in wired erhalten eine `CDynLinkLibrary` Kette, müssen sie erstellen eine `CDynLinkLibrary` Objekt im Kontext von jedem Modul, die sie verwenden möchten. `AfxNetInitModule` erstellt die `CDynLinkLibrary` Objekts in Ihre regulären MFC DLL Kontext, sodass es in wired Ruft die `CDynLinkLibrary` Objekt Kette von der regulären MFC-DLL.

### <a name="requirements"></a>Anforderungen

**Header:** \<afxdll_.h >

### <a name="see-also"></a>Siehe auch

[Makros und globale Variablen](mfc-macros-and-globals.md)<br/>
[AfxMessageBox](cstring-formatting-and-message-box-display.md#afxmessagebox)

## <a name="afxgetambientactctx"></a> AfxGetAmbientActCtx

Verwenden Sie diese Funktion zum Abrufen von des aktuellen Status des pro-Module-Status-Flags, die die WinSxS-Verhalten von MFC wirkt sich auf.

### <a name="syntax"></a>Syntax

```
BOOL AFXAPI AfxGetAmbientActCtx();
```

### <a name="return-value"></a>Rückgabewert

Modul Status aktuellen Wert des Kennzeichens.

### <a name="remarks"></a>Hinweise

Wenn das Flag festgelegt ist (der Standard ist) und ein Thread wechselt in einem MFC-Modul (finden Sie unter [AFX_MANAGE_STATE](#afx_manage_state)), der Kontext des Moduls wird aktiviert.

Wenn das Flag nicht festgelegt ist, ist der Kontext des Moduls auf Eintrag nicht aktiviert.

Der Kontext eines Moduls wird in seinem Manifest eingebettet in der Regel in Modulressourcen bestimmt.

### <a name="requirements"></a>Anforderungen

**Header:** afxcomctl32.h

### <a name="see-also"></a>Siehe auch

[Makros und globale Variablen](mfc-macros-and-globals.md)<br/>
[AFX_MANAGE_STATE](#afx_manage_state)<br/>
[Verwalten der Statusdaten von MFC-Modulen](../managing-the-state-data-of-mfc-modules.md)<br/>
[AfxSetAmbientActCtx](#setambientactctx)

## <a name="afxgetstaticmodulestate"></a> AfxGetStaticModuleState

Mit dieser Funktion wird zum Festlegen des Modulstatus vor der Initialisierung bzw. den vorherigen Zustand nach der Bereinigung wiederherstellen.

### <a name="syntax"></a>Syntax

```
AFX_MODULE_STATE* AFXAPI AfxGetStaticModuleState( );
```

### <a name="return-value"></a>Rückgabewert

Ein Zeiger auf ein `AFX_MODULE_STATE` Struktur.

### <a name="remarks"></a>Hinweise

Die `AFX_MODULE_STATE` Struktur enthält die globale Daten für das Modul, d. h. der Teil der Modulstatus, die mithilfe von Push übertragen oder per pop ausgelesen wird.

Standardmäßig verwendet MFC Ressourcenhandle von der hauptanwendung beim Laden der Ressourcenvorlage an. Wenn Sie eine exportierte Funktion in einer DLL, z. B. ein verfügen, die startet ein Dialogfeld, in der DLL wird mit dieser Vorlage tatsächlich in das DLL-Modul gespeichert. Sie müssen den Zustand für das richtige Handle verwendet werden zu wechseln. Dazu können Sie den folgenden Code am Anfang der Funktion hinzufügen:

```cpp
AFX_MANAGE_STATE(AfxGetStaticModuleState( ));

```

Dies tauscht den aktuellen Modulstatus mit dem Status von zurückgegebenen `AfxGetStaticModuleState` bis zum Ende des aktuellen Gültigkeitsbereichs.

Weitere Informationen zu Modulzustände und MFC, finden Sie unter "Verwalten der Statusdaten von MFC-Modulen" in [Erstellen neuer Dokumente, Windows und Ansichten](../creating-new-documents-windows-and-views.md) und [technischen Hinweis 58](../tn058-mfc-module-state-implementation.md).

### <a name="requirements"></a>Anforderungen

**Header:** afxstat_.h


## <a name="afxinitextensionmodule"></a> AfxInitExtensionModule

Rufen Sie diese Funktion in einer MFC-Erweiterungs-DLL des `DllMain` die DLL nicht initialisieren.

### <a name="syntax"></a>Syntax

```
BOOL AFXAPI AfxInitExtensionModule( AFX_EXTENSION_MODULE& state,  HMODULE hModule );
```
### <a name="parameters"></a>Parameter

*state*<br/>
Ein Verweis auf die [AFX_EXTENSION_MODULE-Struktur](afx-extension-module-structure.md) -Struktur, die den Zustand der MFC-Erweiterungs-DLL-Modul nach der Initialisierung enthalten ist. Dieser Status umfasst eine Kopie der Objekte der Common Language Runtime-Klasse, die als Teil der normal statische Objektkonstruktion ausgeführt, bevor von den MFC-Erweiterungs-DLL initialisiert wurden `DllMain` eingegeben wird.

*hModule*<br/>
Ein Handle für das MFC-Erweiterungs-DLL-Modul.

### <a name="return-value"></a>Rückgabewert

True, wenn die MFC-Erweiterungs-DLL erfolgreich initialisiert wurde. andernfalls "false".

### <a name="remarks"></a>Hinweise

Zum Beispiel:

```cpp
static AFX_EXTENSION_MODULE NVC_MFC_DLLDLL = { NULL, NULL };
extern "C" int APIENTRY
DllMain(HINSTANCE hInstance, DWORD dwReason, LPVOID lpReserved)
{
    // Remove this if you use lpReserved
    UNREFERENCED_PARAMETER(lpReserved);

    if (dwReason == DLL_PROCESS_ATTACH)
    {
        TRACE0("NVC_MFC_DLL.DLL Initializing!\n");

        // MFC extension DLL one-time initialization
        if (!AfxInitExtensionModule(NVC_MFC_DLLDLL, hInstance))
            return 0;

```

`AfxInitExtensionModule` erstellt eine Kopie der DLL HMODULE und erfasst die DLL Runtime-Klassen (`CRuntimeClass` Strukturen) sowie die Objektfactory (`COleObjectFactory` Objekte) für die Verwendung später, wenn die `CDynLinkLibrary` Objekt erstellt wird.
MFC-Erweiterungs-DLLs müssen zwei Dinge in ihre `DllMain` Funktion:
- Rufen Sie [AfxInitExtensionModule](#_mfc_afxinitextensionmodule) und den Rückgabewert überprüfen.
- Erstellen Sie eine `CDynLinkLibrary` Objekt, wenn die DLL exportieren [CRuntimeClass-Struktur](cruntimeclass-structure.md) Objekte oder verfügt über eine eigene benutzerdefinierte Ressourcen.
Rufen Sie `AfxTermExtensionModule` bereinigen Sie die MFC-Erweiterungs-DLL wird jeder Prozess von der MFC-Erweiterungs-DLL getrennt (Dies ist der Fall, wenn der Prozess beendet wird oder die DLL entladen wird, als Ergebnis des ein `AfxFreeLibrary` aufrufen).

### <a name="requirements"></a>Anforderungen

**Header:** afxdll_.h

### <a name="see-also"></a>Siehe auch

[Makros und globale Variablen](mfc-macros-and-globals.md)<br/>
[AfxTermExtensionModule](#afxtermextensionmodule)

## <a name="afxsetambientactctx"></a>  AfxSetAmbientActCtx

Verwenden Sie diese Funktion, um die modulspezifischen Zustand fest, wodurch die WinSxS-Verhalten von MFC wirkt sich auf.

### <a name="syntax"></a>Syntax

  ```
   void AFXAPI AfxSetAmbientActCtx( BOOL bSet
);
```
### <a name="parameters"></a>Parameter

*bSet*<br/>
Neue Wert der das Modul Statusflag.

### <a name="remarks"></a>Hinweise

Wenn das Flag festgelegt ist (der Standard ist) und ein Thread wechselt in einem MFC-Modul (finden Sie unter [AFX_MANAGE_STATE](#afx_manage_state)), der Kontext des Moduls wird aktiviert.
Wenn das Flag nicht festgelegt ist, ist der Kontext des Moduls auf Eintrag nicht aktiviert.
Der Kontext eines Moduls wird in seinem Manifest eingebettet in der Regel in Modulressourcen bestimmt.

### <a name="example"></a>Beispiel

```cpp
BOOL CMFCListViewApp::InitInstance()
{
   AfxSetAmbientActCtx(FALSE);
   // Remainder of function definition omitted.
```

### <a name="requirements"></a>Anforderungen

**Header:** afxcomctl32.h

### <a name="see-also"></a>Siehe auch

[Makros und globale Variablen](mfc-macros-and-globals.md)<br/>
[AfxGetAmbientActCtx](#afxgetambientactctx)<br/>
[AFX_MANAGE_STATE](#afx_manage_state)<br/>
[Verwalten der Statusdaten von MFC-Modulen](../managing-the-state-data-of-mfc-modules.md)

## <a name="afxtermextensionmodule"></a>  AfxTermExtensionModule

Mit dieser Funktion können Sie MFC Bereinigung ermöglichen die MFC-Erweiterungs-DLL wird jeder Prozess von der DLL getrennt (Dies ist der Fall, wenn der Prozess beendet wird oder die DLL entladen wird, aufgrund einer `AfxFreeLibrary` aufrufen).

### <a name="syntax"></a>Syntax

  ```
void AFXAPI AfxTermExtensionModule(  AFX_EXTENSION_MODULE& state,  BOOL bAll  = FALSE );
```
### <a name="parameters"></a>Parameter

*state*<br/>
Ein Verweis auf die [AFX_EXTENSION_MODULE](afx-extension-module-structure.md) -Struktur, die den Zustand der MFC-Erweiterungs-DLL-Modul enthält.

*bAll*<br/>
Wenn "true", Bereinigung, da alle MFC-Erweiterungs-DLL-Module. Andernfalls Bereinigung nur das aktuelle DLL-Modul.

### <a name="remarks"></a>Hinweise

`AfxTermExtensionModule` Löscht alle lokalen Speicher, angefügt an das Modul und entfernen Sie alle Einträge aus dem Cache der Nachricht zuordnen. Zum Beispiel:

```cpp
static AFX_EXTENSION_MODULE NVC_MFC_DLLDLL = { NULL, NULL };
extern "C" int APIENTRY
DllMain(HINSTANCE hInstance, DWORD dwReason, LPVOID lpReserved)
{
    // Remove this if you use lpReserved
    UNREFERENCED_PARAMETER(lpReserved);

    if (dwReason == DLL_PROCESS_ATTACH)
    {
        TRACE0("NVC_MFC_DLL.DLL Initializing!\n");

        // MFC extension DLL one-time initialization
        if (!AfxInitExtensionModule(NVC_MFC_DLLDLL, hInstance))
            return 0;

        new CMyDynLinkLibrary(NVC_MFC_DLLDLL);

    }
    else if (dwReason == DLL_PROCESS_DETACH)
    {
        TRACE0("NVC_MFC_DLL.DLL Terminating!\n");

        // Terminate the library before destructors are called
        AfxTermExtensionModule(NVC_MFC_DLLDLL);
    }
    return 1;   // ok
}

```

Wenn die Anwendung lädt und dynamisch frei von MFC-Erweiterungs-DLLs, müssen Sie unbedingt Aufrufen `AfxTermExtensionModule`. Da die meisten MFC-Erweiterungs-DLLs nicht dynamisch geladen werden werden (in der Regel verknüpft sind über ihre Importbibliotheken), den Aufruf von `AfxTermExtensionModule` ist in der Regel nicht erforderlich.

MFC-Erweiterungs-DLLs aufrufen müssen [AfxInitExtensionModule](#afxinitextensionmodule) in ihre `DllMain`. Wenn die DLL exportieren [CRuntimeClass](cruntimeclass-structure.md) Objekte oder verfügt über eine eigene benutzerdefinierte Ressourcen, müssen Sie auch erstellen eine `CDynLinkLibrary` -Objekt im `DllMain`.

### <a name="requirements"></a>Anforderungen

**Header:** afxdll_.h

### <a name="see-also"></a>Siehe auch

[Makros und globale Variablen](mfc-macros-and-globals.md)<br/>
[AfxInitExtensionModule](#afxinitextensionmodule)





