---
title: Makros und Funktionen zum Verwalten von DLLs | Microsoft Docs
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
ms.openlocfilehash: e5e79556bf6e3ae92f7a8d4975dbd30f199e2ca8
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33376475"
---
# <a name="macros-and-functions-for-managing-dlls"></a>Makros und Funktionen zum Verwalten von DLLs

|||
|-|-|
|[AFX_EXT_CLASS](#afx_ext_class)]|Exporte-Klassen.|
|[AFX_MANAGE_STATE](#afx_manage_state)|Eine exportierte Funktion in einer DLL zu schützen.|
|[AfxOleInitModule](#afxoleinitmodule)|Unterstützt OLE aus einer regulären MFC-DLL, die dynamisch mit MFC verknüpft wird.|
|[AfxNetInitModule](#afxnetinitmodule)|Bietet MFC-Sockets aus einer regulären MFC-DLL, die dynamisch mit MFC verknüpft wird.|
|[AfxGetAmbientActCtx](#afxgetambientactctx)|Ruft den aktuellen Status des pro-Module-Status-Flags ab.|
|[AfxGetStaticModuleState](#afxgetstaticmodulestate)|Legt den Zustand vor der Initialisierung und/oder nach der Bereinigung den vorherigen Zustand wiederherstellen.|
|[AfxInitExtensionModule]()#afxinitextensionmodule|Initialisiert die DLL an.|
|[AfxSetAmbientActCtx](#afxsetambientactctx)|Legen Sie das Statusflag-Module, die das Verhalten WinSxS MFC wirkt sich auf.|
|[AfxTermExtensionModule]()#afxtermextensionmodule)|Können MFC Cleanup der MFC-Erweiterungs-DLL beim jeden Prozess aus der DLL wird getrennt.|


## <a name="afx_ext_class"></a>  AFX_EXT_CLASS
[MFC-Erweiterungs-DLLs](../../build/extension-dlls.md) verwenden Sie das Makro **AFX_EXT_CLASS** zum Exportieren von Klassen, die ausführbaren Dateien, die mit der MFC-Erweiterungs-DLL verknüpft das Makro verwenden, um Klassen zu importieren.  
   
### <a name="remarks"></a>Hinweise  
 Mit der **AFX_EXT_CLASS** -Makro, derselbe Header Datei(en) verwendet, um die MFC-Erweiterungs-DLL erstellen kann mit den ausführbaren Dateien, die mit der DLL verwendet werden.  
  
 Fügen Sie in der Headerdatei für die DLL, die **AFX_EXT_CLASS** Schlüsselwort, um die Deklaration der Klasse wie folgt:  
  
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
 `pModuleState`  
 Ein Zeiger auf eine `AFX_MODULE_STATE` Struktur.  
   
### <a name="remarks"></a>Hinweise  
 Wenn dieses Makro aufgerufen wird, `pModuleState` ist der effektive Modulstatus für den Rest der unmittelbaren enthält Bereich. Beim Verlassen des Bereichs, wird der vorherigen gültigen Modulstatus automatisch wiederhergestellt werden.    
 Die `AFX_MODULE_STATE` Struktur enthält die globale Daten für das Modul, d. h. der Teil der Modulstatus, die per Push übertragen oder per pop ausgelesen wird.    
 Standardmäßig verwendet MFC das Ressourcenhandle von der hauptanwendung, um die Ressourcenvorlage zu laden. Wenn Sie eine exportierte Funktion in einer DLL, z. B. einen verfügen, die ein Dialogfeld, in der DLL wird gestartet wird diese Vorlage tatsächlich in das DLL-Modul gespeichert. Sie müssen das richtige Handle zu verwendende-Modulstatus zu wechseln. Dazu können Sie den folgenden Code am Anfang der Funktion hinzufügen:    
```cpp
AFX_MANAGE_STATE(AfxGetStaticModuleState( ));

```
 Dies tauscht den aktuellen Modulstatus mit dem Status Merry [AfxGetStaticModuleState](#afxgetstaticmodulestate) bis zum Ende des aktuellen Gültigkeitsbereichs.    
 Weitere Informationen zu Modulzustände und MFC, finden Sie unter "Verwalten der Statusdaten von MFC-Modulen" in [Erstellen neuer Dokumente, Fenster und Ansichten](../creating-new-documents-windows-and-views.md) und [technischen Hinweis 58](../tn058-mfc-module-state-implementation.md).    
> [!NOTE]
>  Wenn MFC einen Aktivierungskontext für eine Assembly erstellt, verwendet [AfxWinInit](#afxwininit) um den Kontext zu erstellen und `AFX_MANAGE_STATE` das Aktivieren und deaktivieren es. Beachten Sie auch Folgendes `AFX_MANAGE_STATE` für statischen MFC-Bibliotheken sowie MFC-DLLs aktiviert ist, damit MFC-Code in den richtigen Aktivierungskontext ausgewählt, die von der DLL Benutzer ausführen kann. Weitere Informationen finden Sie unter [Unterstützung für Aktivierungskontexte im MFC-Modulstatus](../support-for-activation-contexts-in-the-mfc-module-state.md).     
### <a name="requirements"></a>Anforderungen  
 **Header:** afxstat_.h  
   
### <a name="see-also"></a>Siehe auch  
 [AfxGetStaticModuleState](#afxgetstaticmodulestate)

## <a name="a-nameafxoleinitmodulea-afxoleinitmodule"></a><a name="afxoleinitmodule"><a/> AfxOleInitModule
Für OLE-Unterstützung aus einer regulären MFC-DLL, die dynamisch mit MFC verknüpft wird, rufen Sie diese Funktion in der regulären MFC DLL `CWinApp::InitInstance` Funktion der MFC-OLE-DLL nicht initialisieren.  
   
### <a name="syntax"></a>Syntax    
```
void AFXAPI AfxOleInitModule( );  
```  
   
### <a name="remarks"></a>Hinweise  
 Die MFC-OLE-DLL ist eine MFC-Erweiterungs-DLL. in der Reihenfolge für eine MFC-Erweiterungs-DLL in wired Abrufen einer **CDynLinkLibrary** Kette, müssen sie erstellen eine **CDynLinkLibrary** Objekt im Kontext von jedem Modul, das sie verwenden möchten. `AfxOleInitModule` erstellt die **CDynLinkLibrary** Objekt im Kontext der regulären MFC DLL, sodass es in wired Ruft die **CDynLinkLibrary** Kette von regulären MFC-DLL-Objekt.  
  
 Wenn Sie beim Erstellen eines OLE-Steuerelements und `COleControlModule`, rufen Sie nicht **AfxOleInitModule** da die `InitInstance` Memberfunktion für `COleControlModule` Aufrufe `AfxOleInitModule`.  
   
### <a name="requirements"></a>Anforderungen  
 **Header**: < afxdll_.h >  
   
### <a name="see-also"></a>Siehe auch  
 [Makros und globale Variablen](mfc-macros-and-globals.md)   
 [AfxMessageBox](cstring-formatting-and-message-box-display.md#afxmessagebox)

## <a name="afxnetinitmodule"></a>  AfxNetInitModule
Für MFC-Sockets aus einer regulären MFC-DLL, die dynamisch mit MFC verknüpft wird unterstützen, fügen Sie einen Aufruf dieser Funktion in der regulären MFC DLL **CWinApp:: InitInstance** Funktion, um die MFC-Sockets-DLL nicht initialisieren.  
   
### <a name="syntax"></a>Syntax    
```
void AFXAPI AfxNetInitModule( );  
```  
   
### <a name="remarks"></a>Hinweise  
 Die MFC-Sockets-DLL ist eine MFC-Erweiterungs-DLL. in der Reihenfolge für eine MFC-Erweiterungs-DLL in wired Abrufen einer **CDynLinkLibrary** Kette, müssen sie erstellen eine **CDynLinkLibrary** Objekt im Kontext von jedem Modul, das sie verwenden möchten. `AfxNetInitModule` erstellt die **CDynLinkLibrary** Objekt im Kontext der regulären MFC DLL, sodass es in wired Ruft die **CDynLinkLibrary** Kette von regulären MFC-DLL-Objekt.  
   
### <a name="requirements"></a>Anforderungen  
 **Header:** < afxdll_.h >  
   
### <a name="see-also"></a>Siehe auch  
 [Makros und globale Variablen](mfc-macros-and-globals.md)   
 [AfxMessageBox](cstring-formatting-and-message-box-display.md#afxmessagebox)

## <a name="afxgetambientactctx"></a> AfxGetAmbientActCtx
Verwenden Sie diese Funktion, um den aktuellen Status der das Statusflag pro Modul abzurufen, bei denen das Verhalten WinSxS MFC wirkt sich auf.  
   
### <a name="syntax"></a>Syntax    
```  
BOOL AFXAPI AfxGetAmbientActCtx();   
```  
   
### <a name="return-value"></a>Rückgabewert  
 Modul Status aktuellen Wert des Kennzeichens.  
   
### <a name="remarks"></a>Hinweise  
 Wenn das Flag festgelegt ist (die Standardeinstellung) und ein Thread wechselt in einem MFC-Modul (finden Sie unter [AFX_MANAGE_STATE](#afx_manage_state)), der Kontext des Moduls wird aktiviert.  
  
 Wenn das Flag nicht festgelegt ist, ist der Kontext des Moduls auf Eintrag nicht aktiviert.  
  
 Der Kontext eines Moduls wird von seinem Manifest eingebettet in der Regel im Modulressourcen bestimmt.  
   
### <a name="requirements"></a>Anforderungen  
 **Header:** afxcomctl32.h  
   
### <a name="see-also"></a>Siehe auch  
 [Makros und globale Variablen](mfc-macros-and-globals.md)   
 [AFX_MANAGE_STATE](#afx_manage_state)   
 [Verwalten der Statusdaten von MFC-Modulen](../managing-the-state-data-of-mfc-modules.md)   
 [AfxSetAmbientActCtx](#setambientactctx)
 
## <a name="afxgetstaticmodulestate"></a> AfxGetStaticModuleState
Mit dieser Funktion wird zum Festlegen des Modulstatus vor der Initialisierung und/oder nach der Bereinigung den vorherigen Zustand wiederherstellen.  
   
### <a name="syntax"></a>Syntax    
```
AFX_MODULE_STATE* AFXAPI AfxGetStaticModuleState( );  
```  
   
### <a name="return-value"></a>Rückgabewert  
 Ein Zeiger auf eine `AFX_MODULE_STATE` Struktur.  
   
### <a name="remarks"></a>Hinweise  
 Die `AFX_MODULE_STATE` Struktur enthält die globale Daten für das Modul, d. h. der Teil der Modulstatus, die per Push übertragen oder per pop ausgelesen wird.  
  
 Standardmäßig verwendet MFC das Ressourcenhandle von der hauptanwendung, um die Ressourcenvorlage zu laden. Wenn Sie eine exportierte Funktion in einer DLL, z. B. einen verfügen, die ein Dialogfeld, in der DLL wird gestartet wird diese Vorlage tatsächlich in das DLL-Modul gespeichert. Sie müssen das richtige Handle zu verwendende-Modulstatus zu wechseln. Dazu können Sie den folgenden Code am Anfang der Funktion hinzufügen:  
  
```cpp
AFX_MANAGE_STATE(AfxGetStaticModuleState( ));

```
  
 Dies tauscht den aktuellen Modulstatus mit dem Status Merry `AfxGetStaticModuleState` bis zum Ende des aktuellen Gültigkeitsbereichs.  
  
 Weitere Informationen zu Modulzustände und MFC, finden Sie unter "Verwalten der Statusdaten von MFC-Modulen" in [Erstellen neuer Dokumente, Fenster und Ansichten](../creating-new-documents-windows-and-views.md) und [technischen Hinweis 58](../tn058-mfc-module-state-implementation.md).  
   
### <a name="requirements"></a>Anforderungen  
 **Header:** afxstat_.h  
   

## <a name="afxinitextensionmodule"></a> AfxInitExtensionModule
Mit dieser Funktion wird in einer MFC-Erweiterungs-DLL des `DllMain` die DLL nicht initialisieren.  
   
### <a name="syntax"></a>Syntax    
```
BOOL AFXAPI AfxInitExtensionModule( AFX_EXTENSION_MODULE& state,  HMODULE hModule );  
```
### <a name="parameters"></a>Parameter  
 `state`  
 Ein Verweis auf die [AFX_EXTENSION_MODULE-Struktur](afx-extension-module-structure.md) -Struktur, die den Zustand der MFC-Erweiterungs-DLL-Modul nach der Initialisierung enthalten wird. Dieser Status umfasst eine Kopie der Objekte der Common Language Runtime-Klasse, die im Rahmen des normalen statische Objektkonstruktion ausgeführt, bevor von den MFC-Erweiterungs-DLL initialisiert wurden `DllMain` eingegeben wird.  
  
 `hModule`  
 Ein Handle des MFC-Erweiterungs-DLL-Modul.  
   
### <a name="return-value"></a>Rückgabewert  
 **"True"** ist die MFC-Erweiterungs-DLL erfolgreich initialisiert wurde, andernfalls **"false"**.  
   
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
  
 `AfxInitExtensionModule` erstellt eine Kopie des DLL **HMODULE** ab und zeichnet die DLL-Runtime-Klassen (`CRuntimeClass` Strukturen) sowie die Objektfactory (`COleObjectFactory` Objekte) für die Verwendung höher bei der **CDynLinkLibrary**Objekt erstellt wird.    
 MFC-Erweiterungs-DLLs müssen zwei Dinge in ihre `DllMain` Funktion:    
-   Rufen Sie [AfxInitExtensionModule](#_mfc_afxinitextensionmodule) und überprüfen den Rückgabewert.   
-   Erstellen einer **CDynLinkLibrary** Objekt, wenn die DLL exportieren [CRuntimeClass Struktur](cruntimeclass-structure.md) Objekte oder verfügt über eine eigene benutzerdefinierte Ressourcen.    
 Sie erreichen `AfxTermExtensionModule` zum Bereinigen von MFC-Erweiterungs-DLL, wenn jeder Prozess von der MFC-Erweiterungs-DLL trennt (das geschieht, wenn der Prozess beendet wird oder wenn die DLL entladen wird, als Ergebnis des ein `AfxFreeLibrary` aufrufen).     

### <a name="requirements"></a>Anforderungen  
 **Header:** afxdll_.h     

### <a name="see-also"></a>Siehe auch  
 [Makros und globale Variablen](mfc-macros-and-globals.md)   
 [AfxTermExtensionModule](#afxtermextensionmodule)

 ## <a name="afxsetambientactctx"></a>  AfxSetAmbientActCtx
Verwenden Sie diese Funktion das WinSxS Verhalten von MFC wirkt sich auf das Statusflag pro Modul festgelegt.  
   
### <a name="syntax"></a>Syntax  
  ```
   void AFXAPI AfxSetAmbientActCtx( BOOL bSet  
);  
```
### <a name="parameters"></a>Parameter  
 `bSet`  
 Neue Wert für das Modul Statusflag.  
   
### <a name="remarks"></a>Hinweise  
 Wenn das Flag festgelegt ist (die Standardeinstellung) und ein Thread wechselt in einem MFC-Modul (finden Sie unter [AFX_MANAGE_STATE](#afx_manage_state)), der Kontext des Moduls wird aktiviert.    
 Wenn das Flag nicht festgelegt ist, ist der Kontext des Moduls auf Eintrag nicht aktiviert.    
 Der Kontext eines Moduls wird von seinem Manifest eingebettet in der Regel im Modulressourcen bestimmt.  
   
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
 [Makros und globale Variablen](mfc-macros-and-globals.md)   
 [AfxGetAmbientActCtx](#afxgetambientactctx)   
 [AFX_MANAGE_STATE](#afx_manage_state)   
 [Verwalten der Statusdaten von MFC-Modulen](../managing-the-state-data-of-mfc-modules.md) 

## <a name="afxtermextensionmodule"></a>  AfxTermExtensionModule

Mit dieser Funktion können MFC bereinigen ermöglichen die MFC-Erweiterungs-DLL, wenn jeder Prozess von der DLL trennt (das geschieht, wenn der Prozess beendet wird oder wenn die DLL entladen wird, als Ergebnis des eine `AfxFreeLibrary` aufrufen).  
   
### <a name="syntax"></a>Syntax  
  ```
void AFXAPI AfxTermExtensionModule(  AFX_EXTENSION_MODULE& state,  BOOL bAll  = FALSE );  
```
### <a name="parameters"></a>Parameter  
 `state`  
 Ein Verweis auf die [AFX_EXTENSION_MODULE](afx-extension-module-structure.md) -Struktur, die den Status des MFC-Erweiterungs-DLL-Modul enthält.  
  
 *Kugel*  
 Wenn **"true"**, bereinigt alle MFC-Erweiterungs-DLL-Module. Andernfalls Cleanup nur das aktuelle DLL-Modul.  
   
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
  
 Wenn die Anwendung lädt und MFC-Erweiterungs-DLLs dynamisch freigegeben, achten Sie darauf Aufrufen `AfxTermExtensionModule`. Da die meisten MFC-Erweiterungs-DLLs nicht dynamisch geladen werden werden (in der Regel verknüpft sind über ihre Importbibliotheken), den Aufruf von `AfxTermExtensionModule` ist in der Regel nicht erforderlich.  
  
 MFC-Erweiterungs-DLLs müssen Aufrufen [AfxInitExtensionModule](#afxinitextensionmodule) in ihre `DllMain`. Wenn die DLL exportieren [CRuntimeClass](cruntimeclass-structure.md) Objekte oder verfügt über eine eigene benutzerdefinierte Ressourcen müssen Sie auch zum Erstellen einer **CDynLinkLibrary** -Objekt in `DllMain`.  
   
### <a name="requirements"></a>Anforderungen  
 **Header:** afxdll_.h  
   
### <a name="see-also"></a>Siehe auch  
 [Makros und globale Variablen](mfc-macros-and-globals.md)   
 [AfxInitExtensionModule](#afxinitextensionmodule)
 




