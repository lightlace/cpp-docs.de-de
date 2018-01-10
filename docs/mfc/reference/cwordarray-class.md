---
title: CWordArray Klasse | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CWordArray
- AFXCOLL/CWordArray
- AFXCOLL/CObArray::CObArray
- AFXCOLL/CObArray::Add
- AFXCOLL/CObArray::Append
- AFXCOLL/CObArray::Copy
- AFXCOLL/CObArray::ElementAt
- AFXCOLL/CObArray::FreeExtra
- AFXCOLL/CObArray::GetAt
- AFXCOLL/CObArray::GetCount
- AFXCOLL/CObArray::GetData
- AFXCOLL/CObArray::GetSize
- AFXCOLL/CObArray::GetUpperBound
- AFXCOLL/CObArray::InsertAt
- AFXCOLL/CObArray::IsEmpty
- AFXCOLL/CObArray::RemoveAll
- AFXCOLL/CObArray::RemoveAt
- AFXCOLL/CObArray::SetAt
- AFXCOLL/CObArray::SetAtGrow
- AFXCOLL/CObArray::SetSize
dev_langs: C++
helpviewer_keywords:
- CObArray [MFC], CObArray
- CObArray [MFC], Add
- CObArray [MFC], Append
- CObArray [MFC], Copy
- CObArray [MFC], ElementAt
- CObArray [MFC], FreeExtra
- CObArray [MFC], GetAt
- CObArray [MFC], GetCount
- CObArray [MFC], GetData
- CObArray [MFC], GetSize
- CObArray [MFC], GetUpperBound
- CObArray [MFC], InsertAt
- CObArray [MFC], IsEmpty
- CObArray [MFC], RemoveAll
- CObArray [MFC], RemoveAt
- CObArray [MFC], SetAt
- CObArray [MFC], SetAtGrow
- CObArray [MFC], SetSize
ms.assetid: 2ba2c194-2c6c-40ff-9db4-e9dbe57e1f57
caps.latest.revision: "26"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 5804df97c54a111a02b79dc849c20c91ba8176b7
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="cwordarray-class"></a>CWordArray-Klasse
Unterstützt Arrays mit 16-Bit-Wörtern.  
  
## <a name="syntax"></a>Syntax  
  
```  
class CWordArray : public CObject  
```  
  
## <a name="members"></a>Member  
 Die Memberfunktionen von `CWordArray` ähneln den Memberfunktionen der Klasse [CObArray](../../mfc/reference/cobarray-class.md). Aufgrund dieser Ähnlichkeit können Sie die `CObArray`-Referenzdokumentation für Memberfunktionsbesonderheiten verwenden. Immer dort, wo eine [CObject](../../mfc/reference/cobject-class.md) Zeiger als Funktionsparameter oder Rückgabewert, ersetzen Sie durch eine **WORD**.  
  
 `CObject* CObArray::GetAt( int <nIndex> ) const;`  
  
 Beispielsweise übersetzt zu  
  
 `WORD CWordArray::GetAt( int <nIndex> ) const;`  
  
### <a name="public-constructors"></a>Öffentliche Konstruktoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CObArray::CObArray](../../mfc/reference/cobarray-class.md#cobarray)|Erstellt ein leeres Array.|  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CObArray::Add](../../mfc/reference/cobarray-class.md#add)|Fügt am Ende des Arrays ein Element hinzu; vergrößert das Array bei Bedarf.|  
|[CObArray::Append](../../mfc/reference/cobarray-class.md#append)|Hängt ein anderes Array an das Array an; vergrößert das Array bei Bedarf.|  
|[CObArray::Copy](../../mfc/reference/cobarray-class.md#copy)|Kopiert ein anderes Array in das Array; vergrößert das Array bei Bedarf.|  
|[CObArray::ElementAt](../../mfc/reference/cobarray-class.md#elementat)|Gibt einen temporären Verweis auf den Elementzeiger innerhalb des Arrays zurück.|  
|[CObArray::FreeExtra](../../mfc/reference/cobarray-class.md#freeextra)|Gibt den gesamten nicht verwendeten Arbeitsspeicher über der aktuellen Obergrenze frei.|  
|[CObArray::GetAt](../../mfc/reference/cobarray-class.md#getat)|Gibt den Wert an einem bestimmten Index zurück.|  
|[CObArray::GetCount](../../mfc/reference/cobarray-class.md#getcount)|Ruft die Anzahl der Elemente im Array ab.|  
|[CObArray::GetData](../../mfc/reference/cobarray-class.md#getdata)|Ermöglicht den Zugriff auf Elemente im Array. Kann **NULL**.|  
|[CObArray::GetSize](../../mfc/reference/cobarray-class.md#getsize)|Ruft die Anzahl der Elemente im Array ab.|  
|[CObArray::GetUpperBound](../../mfc/reference/cobarray-class.md#getupperbound)|Gibt den größten gültigen Index zurück.|  
|[CObArray::InsertAt](../../mfc/reference/cobarray-class.md#insertat)|Fügt ein Element (oder alle Elemente in einem anderen Array) am angegebenen Index ein.|  
|[CObArray::IsEmpty](../../mfc/reference/cobarray-class.md#isempty)|Bestimmt, ob das Array leer ist.|  
|[CObArray::RemoveAll](../../mfc/reference/cobarray-class.md#removeall)|Entfernt alle Elemente aus diesem Array.|  
|[CObArray::RemoveAt](../../mfc/reference/cobarray-class.md#removeat)|Entfernt ein Element an einem spezifischen Index.|  
|[CObArray::SetAt](../../mfc/reference/cobarray-class.md#setat)|Legt den Wert für einen bestimmten Index fest; Array darf nicht vergrößert werden.|  
|[CObArray::SetAtGrow](../../mfc/reference/cobarray-class.md#setatgrow)|Legt den Wert für einen bestimmten Index fest; vergrößert das Array bei Bedarf.|  
|[CObArray::SetSize](../../mfc/reference/cobarray-class.md#setsize)|Legt die Anzahl der Elemente im Array fest.|  
  
### <a name="public-operators"></a>Öffentliche Operatoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CObArray::operator &#91; &#93;](../../mfc/reference/cobarray-class.md#operator_at)|Legt das Element am angegebenen Index fest oder ruft es ab.|  
  
## <a name="remarks"></a>Hinweise  
 `CWordArray`enthält die [IMPLEMENT_SERIAL](run-time-object-model-services.md#implement_serial) -Makro für die Unterstützung von Serialisierung laufzeittypenzugriff und zum Sichern der Elemente. Wenn ein Array von Wörtern in ein Archiv, das entweder mit einem überladenen Operator zum Einfügen oder mit gespeichert ist die [Einfügeoperatoren](../../mfc/reference/cobject-class.md#serialize) Memberfunktion jedes Element ist, was wiederum serialisiert.  
  
> [!NOTE]
>  Vor dem Verwenden eines Arrays, verwenden Sie `SetSize`, um dessen Größe festzustellen, und weisen dafür Arbeitsspeicher zu. Wenn Sie `SetSize` nicht verwenden, kann das Hinzufügen von Elementen zu Ihrem Array dazu führen, dass es häufig neu zugeordnet und kopiert wird. Häufige Neuzuordnungen und Kopiervorgänge sind ineffizient und können zu einer Fragmentierung des Arbeitsspeichers führen.  
  
 Wenn Sie eine Sicherung einzelner Elemente im Array benötigen, müssen Sie die Tiefe des sicherungskontexts auf 1 oder größer festlegen.  
  
 Weitere Informationen zur Verwendung von `CWordArray`, finden Sie im Artikel [Sammlungen](../../mfc/collections.md).  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 `CWordArray`  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** afxcoll.h  
  
##  <a name="icommandsource_interface"></a>ICommandSource-Schnittstelle  
 Verwaltet die Befehle, die von einem Befehlsquellobjekt in einem Benutzersteuerelement gesendet.  
  
```  
interface class ICommandSource  
```  
  
### <a name="remarks"></a>Hinweise  
 Wenn Sie ein benutzerdefiniertes Steuerelement in einer MFC-Ansicht hosten [CWinFormsView Class](../../mfc/reference/cwinformsview-class.md) Routen Befehle und Update-Befehl UI Nachrichten auf das Benutzersteuerelement, damit Sie die MFC-Befehle (z. B. Frame Menüelemente und Symbolleisten-Schaltflächen) verarbeiten kann. Durch die Implementierung, Sie geben dem Benutzersteuerelement einen Verweis auf die `ICommandSource` Objekt.  
  
 Finden Sie unter [wie: Hinzufügen Befehlsrouting zum Windows Forms-Steuerelements](../../dotnet/how-to-add-command-routing-to-the-windows-forms-control.md) ein Beispiel zum Verwenden von `ICommandTarget`.  
  
 Weitere Informationen zur Verwendung von Windows Forms finden Sie unter [Verwenden eines Windows Form-Benutzersteuerelements in MFC](../../dotnet/using-a-windows-form-user-control-in-mfc.md).  
  
##  <a name="addcommandhandler"></a>ICommandSource::AddCommandHandler  
 Eine Befehlsquellobjekt hinzugefügt Befehlshandler.  
  
```  
void AddCommandHandler(
    unsigned int cmdID,  
    CommandHandler^ cmdHandler);
```  
  
### <a name="parameters"></a>Parameter  
 `cmdID`  
 Die Befehls-ID.  
  
 `cmdHandler`  
 Ein Handle für die Handlermethode.  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode fügt Befehlshandler `cmdHandler` mit dem Befehlsquellobjekt und ordnet Sie den Ereignishandler `cmdID`.  
  
 Finden Sie unter [wie: Hinzufügen Befehlsrouting zum Windows Forms-Steuerelements](../../dotnet/how-to-add-command-routing-to-the-windows-forms-control.md) ein Beispiel zum Verwenden von `AddCommandHandler`.  
  
##  <a name="addcommandrangehandler"></a>ICommandSource::AddCommandRangeHandler  
 Ein Befehl Quellobjekt, das hinzugefügt eine Gruppe von Befehlshandler.  
  
```  
void AddCommandRangeHandler(
    unsigned int cmdIDMin,  
    unsigned int cmdIDMax,  
    CommandHandler^ cmdHandler);
```  
  
### <a name="parameters"></a>Parameter  
 `cmdIDMin`  
 Der Anfangsindex der Befehls-ID-Bereich.  
  
 `cmdIDMax`  
 Der Endindex der Befehls-ID-Bereich.  
  
 `cmdHandler`  
 Ein Handle für die Message-Handler-Methode, die die Befehle zugeordnet sind.  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode ordnet einen zusammenhängenden Bereich von Befehls-IDs an einen einzelnen Meldungshandler und das Befehlsquellobjekt hinzugefügt. Dies wird verwendet, für die Behandlung einer Gruppenstatus von verwandten Schaltflächen mit einer Methode.  
  
##  <a name="addcommandrangeuihandler"></a>ICommandSource::AddCommandRangeUIHandler  
 Ein Befehl Quellobjekt, das hinzugefügt eine Gruppe von Benutzer Schnittstelle Befehlshandler Nachricht.  
  
```  
void AddCommandRangeUIHandler(
    unsigned int cmdIDMin,   
    unsigned int cmdIDMax,   
    CommandUIHandler^ cmdUIHandler);
```  
  
### <a name="parameters"></a>Parameter  
 `cmdIDMin`  
 Der Anfangsindex der Befehls-ID-Bereich.  
  
 `cmdIDMax`  
 Der Endindex der Befehls-ID-Bereich.  
  
 `cmdHandler`  
 Ein Handle für die Message-Handler-Methode, die die Befehle zugeordnet sind.  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode ordnet einen zusammenhängenden Bereich von Befehls-IDs an einen einzelnen Benutzer Schnittstelle Befehl-Meldungshandler und das Befehlsquellobjekt hinzugefügt. Dies wird verwendet, für die Behandlung einer Gruppenstatus von verwandten Schaltflächen mit einer Methode.  
  
##  <a name="addcommanduihandler"></a>ICommandSource::AddCommandUIHandler  
 Ein Befehlsobjekt für die Quelle hinzugefügt einen Benutzer-Schnittstelle Befehlshandler Nachricht.  
  
```  
void AddCommandUIHandler(
    unsigned int cmdID,   
    CommandUIHandler^ cmdUIHandler);
```  
  
### <a name="parameters"></a>Parameter  
 `cmdID`  
 Die Befehls-ID.  
  
 `cmdUIHandler`  
 Ein Handle für die Benutzer-Schnittstelle Befehl Message-Handler-Methode.  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode fügt den Benutzer Schnittstelle Befehl Message-Handler `cmdHandler` mit dem Befehlsquellobjekt und ordnet Sie den Ereignishandler `cmdID`.  
  
##  <a name="postcommand"></a>ICommandSource::PostCommand  
 Sendet eine Meldung ohne zu warten, bis sie verarbeitet werden.  
  
```  
void PostCommand(unsigned int command);
```  
  
### <a name="parameters"></a>Parameter  
 `command`  
 Die Befehls-ID der Nachricht gesendet werden.  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode asynchron sendet die Nachricht an die angegebene ID zugeordnet `command`. Sie ruft [CWnd::PostMessage](../../mfc/reference/cwnd-class.md#postmessage) , die Nachricht in die Nachrichtenwarteschlange und gibt dann des Fensters zu platzieren, ohne warten auf das entsprechende Fenster zum Verarbeiten der Nachricht.  
  
##  <a name="removecommandhandler"></a>ICommandSource::RemoveCommandHandler  
 Entfernt einen Befehlshandler von einem Befehl-Quellobjekt.  
  
```  
void RemoveCommandHandler(unsigned int cmdID);
```  
  
### <a name="parameters"></a>Parameter  
 `cmdID`  
 Die Befehls-ID.  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode entfernt die Befehlshandler zugeordnet `cmdID` aus dem Befehlsquellobjekt.  
  
##  <a name="removecommandrangehandler"></a>ICommandSource::RemoveCommandRangeHandler  
 Entfernt eine Gruppe von Befehlshandler von einem Befehl-Quellobjekt.  
  
```  
void RemoveCommandRangeUIHandler(
    unsigned int cmdIDMin,  
    unsigned int cmdIDMax);
```  
  
### <a name="parameters"></a>Parameter  
 `cmdIDMin`  
 Der Anfangsindex der Befehls-ID-Bereich.  
  
 `cmdIDMax`  
 Der Endindex der Befehls-ID-Bereich.  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode entfernt eine Gruppe von Meldungshandler, durch die Befehls-IDs angegeben zugeordnet `cmdIDMin` und `cmdIDMax`, aus dem Befehlsquellobjekt.  
  
##  <a name="removecommandrangeuihandler"></a>ICommandSource::RemoveCommandRangeUIHandler  
 Entfernt eine Gruppe von Benutzer Schnittstelle Befehlshandler Nachricht von einem Befehl-Quellobjekt.  
  
```  
void RemoveCommandRangeUIHandler(
    unsigned int cmdIDMin,  
    unsigned int cmdIDMax);
```  
  
### <a name="parameters"></a>Parameter  
 `cmdIDMin`  
 Der Anfangsindex der Befehls-ID-Bereich.  
  
 `cmdIDMax`  
 Der Endindex der Befehls-ID-Bereich.  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode entfernt eine Gruppe von Benutzer-Schnittstelle Befehl Meldungshandler, durch die Befehls-IDs angegeben zugeordnet `cmdIDMin` und `cmdIDMax`, aus dem Befehlsquellobjekt.  
  
##  <a name="removecommanduihandler"></a>ICommandSource::RemoveCommandUIHandler  
 Entfernt einen Benutzer Schnittstelle Befehlshandler Nachricht von einem Befehl-Quellobjekt.  
  
```  
void RemoveCommandUIHandler(unsigned int cmdID);
```  
  
### <a name="parameters"></a>Parameter  
 `cmdID`  
 Die Befehls-ID.  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode entfernt den Benutzer Schnittstelle Befehl-Meldungshandler zugeordnet `cmdID` aus dem Befehlsquellobjekt.  
  
##  <a name="sendcommand"></a>ICommandSource::SendCommand  
 Sendet eine Nachricht und wartet, bis er vor der Rückgabe verarbeitet werden.  
  
```  
void SendCommand(unsigned int command);
```  
  
### <a name="parameters"></a>Parameter  
 `command`  
 Die Befehls-ID der Nachricht gesendet werden.  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode synchron sendet die Nachricht an die angegebene ID zugeordnet `command`. Sie ruft [Funktion CWnd:: SendMessage](../../mfc/reference/cwnd-class.md#sendmessage) , platzieren die Nachricht in des Fensters Nachrichtenwarteschlange und wartet, bis diese Fensterprozedur die Nachricht vor der Rückgabe verarbeitet hat.  
  
##  <a name="icommandtarget_interface"></a>ICommandTarget-Schnittstelle  
 Bietet eine Schnittstelle zum Empfangen Befehle von einem Befehlsquellobjekt ein Benutzersteuerelement hinzu.  
  
```  
interface class ICommandTarget  
```  
  
### <a name="remarks"></a>Hinweise  
 Wenn Sie ein benutzerdefiniertes Steuerelement in einer MFC-Ansicht hosten [CWinFormsView](../../mfc/reference/cwinformsview-class.md) Routen Befehle und Update-Befehl UI Nachrichten auf das Benutzersteuerelement, damit Sie die MFC-Befehle (z. B. Frame Menüelemente und Symbolleisten-Schaltflächen) verarbeiten kann. Durch die Implementierung `ICommandTarget`, Sie geben dem Benutzersteuerelement einen Verweis auf das Objekt.  
  
 Finden Sie unter [wie: Hinzufügen Befehlsrouting zum Windows Forms-Steuerelements](../../dotnet/how-to-add-command-routing-to-the-windows-forms-control.md) ein Beispiel zum Verwenden von `ICommandTarget`.  
  
 Weitere Informationen zur Verwendung von Windows Forms finden Sie unter [Verwenden eines Windows Form-Benutzersteuerelements in MFC](../../dotnet/using-a-windows-form-user-control-in-mfc.md).  
  
##  <a name="initialize"></a>ICommandTarget:: Initialize  
 Initialisiert das Zielobjekt für den Befehl.  
  
```  
void Initialize(ICommandSource^ cmdSource);
```  
  
### <a name="parameters"></a>Parameter  
 `cmdSource`  
 Ein Handle für das Quellobjekt für den Befehl.  
  
### <a name="remarks"></a>Hinweise  
 Wenn Sie ein benutzerdefiniertes Steuerelement in einer MFC-Ansicht hosten [CWinFormsView](../../mfc/reference/cwinformsview-class.md) Routen Befehle und Update-Befehl UI Nachrichten auf das Benutzersteuerelement zum Behandeln von MFC-Befehle zuzulassen.  
  
 Diese Methode initialisiert die Ziel-Befehlsobjekt und ordnet das Quellobjekt für den angegebenen Befehl `cmdSource`. Es sollte in der Implementierung des Benutzersteuerelements Klasse aufgerufen werden. Bei der Initialisierung, sollten Sie Befehlshandler mit das Befehlsquellobjekt registrieren, durch den Aufruf [ICommandSource::AddCommandHandler](../../mfc/reference/icommandsource-interface.md) in die `Initialize` Implementierung. Finden Sie unter [wie: Hinzufügen Befehlsrouting zum Windows Forms-Steuerelements](../../dotnet/how-to-add-command-routing-to-the-windows-forms-control.md) ein Beispiel zum Verwenden von `Initialize` dazu.  
  
##  <a name="icommandui_interface"></a>ICommandUI-Schnittstelle  
 Verwaltet von Befehlen der Benutzeroberfläche.  
  
```  
interface class ICommandUI  
```  
  
### <a name="remarks"></a>Hinweise  
 Diese Schnittstelle bietet Methoden und Eigenschaften, die Befehlen der Benutzeroberfläche verwalten. `ICommandUI`ähnelt dem [CCmdUI-Klasse](../../mfc/reference/ccmdui-class.md), außer dass `ICommandUI` für MFC-Anwendungen, die mit Visual Studio .NET Komponenten Zusammenwirken verwendet.  
  
 `ICommandUI`wird verwendet, in einer `ON_UPDATE_COMMAND_UI` Handler in einer - abgeleitete Klasse. Wenn ein Benutzer einer Anwendung (SELECT-Anweisungen oder Klicks) aktiviert wird ein Menü, jede Menüelement angezeigt, als aktiviert oder deaktiviert. Das Ziel jeder Menübefehl stellt diese Informationen durch die Implementierung einer `ON_UPDATE_COMMAND_UI` Handler. Verwenden Sie für jeden Befehl Schnittstelle Benutzerobjekte in der Anwendung des Eigenschaftenfensters zum Erstellen einer Meldungszuordnungseintrags und Funktionsprototyp für jeden Handler.  
  
 Weitere Informationen darüber, wie der `ICommandUI` Schnittstelle in Befehlsrouting verwendet wird, finden Sie unter [wie: Hinzufügen Befehlsrouting zum Windows Forms-Steuerelements](../../dotnet/how-to-add-command-routing-to-the-windows-forms-control.md).  
  
 Weitere Informationen zur Verwendung von Windows Forms finden Sie unter [Verwenden eines Windows Form-Benutzersteuerelements in MFC](../../dotnet/using-a-windows-form-user-control-in-mfc.md).  
  
 Weitere Informationen wie Benutzeroberflächenbefehlen in MFC verwaltet werden, finden Sie unter [CCmdUI-Klasse](../../mfc/reference/ccmdui-class.md).  
  
##  <a name="check"></a>ICommandUI::Check  
 Legt die Benutzer-Schnittstelle-Element für diesen Befehl auf den entsprechenden Aktivierungszustand fest.  
  
```  
property UICheckState Check;  
```  
  
### <a name="remarks"></a>Hinweise  
 Diese Eigenschaft legt die Benutzer-Schnittstelle-Element für diesen Befehl auf den entsprechenden Aktivierungszustand an. Legen Sie `Check` auf die folgenden Werte:  
  
|Begriff|Definition|  
|----------|----------------|  
|0|Deaktivieren Sie|  
|1|Kontrollkästchen|  
|2|Unbestimmt festlegen|  
  
##  <a name="continuerouting"></a>ICommandUI::ContinueRouting  
 Weist den Befehl Routingmechanismus dar, um den Vorgang fortzusetzen, routing von der aktuellen Nachricht unten die Kette der Handler.  
  
```  
void ContinueRouting();
```  
  
### <a name="remarks"></a>Hinweise  
 Dies ist eine erweiterte Memberfunktion, die in Verbindung mit verwendet werden soll ein [ON_COMMAND_EX](message-map-macros-mfc.md#on_command_ex) Handler, der gibt `FALSE`. Weitere Informationen finden Sie im technischen Hinweis [TN006: Meldungszuordnungen](../../mfc/tn006-message-maps.md).  
  
##  <a name="enabled"></a>ICommandUI::Enabled  
 Aktiviert oder deaktiviert die Benutzer-Schnittstelle-Element für diesen Befehl.  
  
```  
property bool Enabled;  
```  
  
### <a name="remarks"></a>Hinweise  
 Diese Eigenschaft aktiviert oder deaktiviert die Benutzer-Schnittstelle-Element für diesen Befehl. Legen Sie `Enabled` auf `TRUE` So aktivieren Sie das Element `FALSE` zu deaktivieren.  
  
##  <a name="id"></a>ICommandUI::ID  
 Ruft die ID des Benutzerobjekts für die Schnittstelle dargestellt, die durch die `ICommandUI` Objekt.  
  
```  
property unsigned int ID;  
```  
  
### <a name="remarks"></a>Hinweise  
 Diese Eigenschaft ruft die ID (ein Handle) des Menüelements, Symbolleisten-Schaltfläche oder durch andere Benutzer-Schnittstellenobjekt dargestellt die `ICommandUI` Objekt.  
  
##  <a name="index"></a>ICommandUI::Index  
 Ruft den Index des dem Benutzer-Schnittstellenobjekt, dargestellt durch die `ICommandUI` Objekt.  
  
```  
property unsigned int Index;  
```  
  
### <a name="remarks"></a>Hinweise  
 Diese Eigenschaft ruft den Index (ein Handle) des Menüelements, Symbolleisten-Schaltfläche oder andere Benutzeroberflächen-Objekt dargestellt wird, durch die `ICommandUI` Objekt.  
  
##  <a name="radio"></a>ICommandUI::Radio  
 Legt die Benutzer-Schnittstelle-Element für diesen Befehl auf den entsprechenden Aktivierungszustand fest.  
  
```  
property bool Radio;  
```  
  
### <a name="remarks"></a>Hinweise  
 Diese Eigenschaft legt die Benutzer-Schnittstelle-Element für diesen Befehl auf den entsprechenden Aktivierungszustand an. Legen Sie `Radio` auf `TRUE` So aktivieren Sie das Element; andernfalls `FALSE`.  
  
##  <a name="text"></a>ICommandUI::Text  
 Legt den Text des Elements Schnittstelle Benutzer für diesen Befehl fest.  
  
```  
property String^ Text;  
```  
  
### <a name="remarks"></a>Hinweise  
 Diese Eigenschaft legt den Text des Elements Schnittstelle Benutzer für diesen Befehl fest. Legen Sie `Text` an ein Text-Zeichenfolge-Handle.  
  
##  <a name="iview_interface"></a>IView-Schnittstelle  
 Implementiert mehrere Möglichkeiten, [CWinFormsView](../../mfc/reference/cwinformsview-class.md) zum Senden von Benachrichtigungen anzeigen, die an eine verwaltete Steuerelement verwendet.  
  
```  
interface class IView  
```  
  
### <a name="remarks"></a>Hinweise  
 `IView`implementiert mehrere Möglichkeiten, `CWinFormsView` verwendet, um allgemeine Benachrichtigungen anzeigen, die zu einem verwalteten gehosteten Steuerelement weiterzuleiten. Hierbei handelt es sich [OnInitialUpdate](../../mfc/reference/iview-interface.md), [OnUpdate](../../mfc/reference/iview-interface.md) und [OnActivateView](../../mfc/reference/iview-interface.md).  
  
 `IView`ähnelt dem [CView](../../mfc/reference/cview-class.md), aber nur mit verwalteten Ansichten und Steuerelemente verwendet wird.  
  
 Weitere Informationen zur Verwendung von Windows Forms finden Sie unter [Verwenden eines Windows Form-Benutzersteuerelements in MFC](../../dotnet/using-a-windows-form-user-control-in-mfc.md).  
  
##  <a name="onactivateview"></a>IView::OnActivateView  
 Wird von MFC aufgerufen, wenn eine Sicht aktiviert oder deaktiviert ist.  
  
```  
void OnActivateView(bool activate);
```  
  
### <a name="parameters"></a>Parameter  
 `activate`  
 Gibt an, ob die Sicht wird aktiviert oder deaktiviert.  
  
##  <a name="oninitialupdate"></a>IView:: OnInitialUpdate  
 Vom Framework aufgerufen, nachdem die Ansicht zuerst an das Dokument angefügt ist, aber bevor die Ansicht anfänglich angezeigt wird.  
  
```  
void OnInitialUpdate();
```  
  
##  <a name="onupdate"></a>IView::OnUpdate  
 Wird von MFC aufgerufen, nachdem die Ansicht Dokument geändert wurde.  
  
```  
void OnUpdate();
```  
  
### <a name="remarks"></a>Hinweise  
 Mit dieser Funktion können die Ansicht, um die Aktualisierung der Anzeige, um Änderungen widerzuspiegeln.  
  
## <a name="see-also"></a>Siehe auch  
 [MFC-Beispiel erfassen](../../visual-cpp-samples.md)   
 [CObject-Klasse](../../mfc/reference/cobject-class.md)   
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)



