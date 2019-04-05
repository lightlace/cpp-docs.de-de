---
title: 'Vorgehensweise: Aktivieren und Verwenden einer Windows-Runtime-Komponente mit WRL'
ms.date: 11/04/2016
ms.topic: reference
ms.assetid: 54828f02-6af3-45d1-b965-d0104442f8d5
ms.openlocfilehash: 8c0bed825f76fdf0f2c5cc1fa095e54f08bb8a67
ms.sourcegitcommit: c7f90df497e6261764893f9cc04b5d1f1bf0b64b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/05/2019
ms.locfileid: "59037211"
---
# <a name="how-to-activate-and-use-a-windows-runtime-component-using-wrl"></a>Vorgehensweise: Aktivieren und Verwenden einer Windows-Runtime-Komponente mit WRL

In diesem Dokument wird gezeigt, wie der Windows Runtime C++ Template Library (WRL) verwenden, um die Windows-Runtime zu initialisieren und das Aktivieren und Verwenden einer Windows-Runtime-Komponente.

Um eine Komponente zu verwenden, müssen Sie einen Schnittstellenzeiger auf den Typ abrufen, der von der Komponente implementiert wird. Und da die zugrunde liegende Technologie der Windows-Runtime das Component Object Model (COM) ist, führen Sie COM-Regeln, um eine Instanz des Typs zu gewährleisten. Sie müssen z. B. verwalten die *Verweiszähler* , der bestimmt, wenn der Typ aus dem Arbeitsspeicher gelöscht wird.

Um die Verwendung der Windows-Runtime zu vereinfachen, stellt Windows Runtime C++ Template Library die intelligenten Zeiger-Vorlage bereit, mit denen [ComPtr\<T >](comptr-class.md), der verweiszählung automatisch ausgeführt. Wenn Sie eine Variable deklarieren, geben `ComPtr<` *Schnittstellenname* `>` *Bezeichner*. Um auf einen Schnittstellenmember zuzugreifen, wenden Sie den Pfeilmemberzugriffsoperator (`->`) auf den Bezeichner an.

> [!IMPORTANT]
> Wenn Sie eine Schnittstellenfunktion aufrufen, testen Sie immer den HRESULT-Rückgabewert.

## <a name="activating-and-using-a-windows-runtime-component"></a>Aktivieren und Verwenden einer Windows Runtime-Komponente

Die folgenden Schritte verwenden den `Windows::Foundation::IUriRuntimeClass` Schnittstelle zu veranschaulichen, wie Sie eine aktivierungsfactory für eine Windows-Runtime-Komponente erstellen, erstellen Sie eine Instanz dieser Komponente und einen Eigenschaftswert abrufen. Außerdem wird gezeigt, wie Sie die Windows-Runtime zu initialisieren. Im Folgenden finden Sie das vollständige Beispiel.

> [!IMPORTANT]
> Obwohl Sie in der Regel über die Windows Runtime C++ Template Library in einer app für die universelle Windows-Plattform (UWP) verwenden, wird in diesem Beispiel eine Konsolen-app zur Veranschaulichung verwendet. Funktionen wie `wprintf_s` sind bei einer UWP-app nicht verfügbar. Weitere Informationen über die Typen und Funktionen, die Sie in einer UWP-app verwenden können, finden Sie unter [in apps der universellen Windows-Plattform nicht unterstützte CRT-Funktionen](../../cppcx/crt-functions-not-supported-in-universal-windows-platform-apps.md) und [Win32 und COM für UWP-apps](/uwp/win32-and-com/win32-and-com-for-uwp-apps).

#### <a name="to-activate-and-use-a-windows-runtime-component"></a>So aktivieren und verwenden Sie eine Windows Runtime-Komponente

1. Enthalten (`#include`) alle erforderlichen Windows-Runtime, die Windows Runtime C++ Template Library und die Header der C++-Standardbibliothek.

   [!code-cpp[wrl-consume-component#2](../codesnippet/CPP/how-to-activate-and-use-a-windows-runtime-component-using-wrl_1.cpp)]

   Es wird empfohlen, den Code mithilfe der `using namespace`-Direktive in der CPP-Datei verständlicher zu gestalten.

2. Initialisieren Sie den Thread, in dem die App ausgeführt wird. Jede App muss ihren Thread und ihr Threadingmodell initialisieren. Dieses Beispiel verwendet die [Microsoft::WRL::Wrappers::RoInitializeWrapper](roinitializewrapper-class.md) zum Initialisieren der Windows-Runtime-Klasse und gibt [RO_INIT_MULTITHREADED](/windows/desktop/api/roapi/ne-roapi-ro_init_type) als Threadingmodell. Die `RoInitializeWrapper`-Klasse ruft `Windows::Foundation::Initialize` auf, wenn sie erstellt, und `Windows::Foundation::Uninitialize`, wenn sie zerstört wird.

   [!code-cpp[wrl-consume-component#3](../codesnippet/CPP/how-to-activate-and-use-a-windows-runtime-component-using-wrl_2.cpp)]

   In der zweiten Anweisung die [roinitializewrapper:: HRESULT](roinitializewrapper-class.md#hresult) -Operator gibt die `HRESULT` aus dem Aufruf von `Windows::Foundation::Initialize`.

3. Erstellen Sie eine *aktivierungsfactory* für die `ABI::Windows::Foundation::IUriRuntimeClassFactory` Schnittstelle.

   [!code-cpp[wrl-consume-component#4](../codesnippet/CPP/how-to-activate-and-use-a-windows-runtime-component-using-wrl_3.cpp)]

   Die Windows-Runtime verwendet den vollqualifizierten Namen, um Typen zu identifizieren. Die `RuntimeClass_Windows_Foundation_Uri` Parameter ist eine Zeichenfolge, die von der Windows-Runtime bereitgestellt wird und den erforderlichen ablaufklassennamen enthält.

4. Initialisiert eine [Microsoft::WRL::Wrappers::HString](hstring-class.md) Variable, die den URI darstellt `"http://www.microsoft.com"`.

   [!code-cpp[wrl-consume-component#6](../codesnippet/CPP/how-to-activate-and-use-a-windows-runtime-component-using-wrl_4.cpp)]

   In der Windows-Runtime nicht Arbeitsspeicher nach einer Zeichenfolge belegt werden, die die Windows-Runtime verwendet werden. Stattdessen erstellt die Windows-Runtime eine Kopie der Zeichenfolge in einem Puffer, die er verwaltet und für Vorgänge verwendet, und gibt ein Handle an den Puffer, dass sie erstellt.

5. Erstellen Sie mit der `IUriRuntimeClassFactory::CreateUri`-Factorymethode ein `ABI::Windows::Foundation::IUriRuntimeClass`-Objekt.

   [!code-cpp[wrl-consume-component#7](../codesnippet/CPP/how-to-activate-and-use-a-windows-runtime-component-using-wrl_5.cpp)]

6. Rufen Sie die `IUriRuntimeClass::get_Domain`-Methode auf, um den Wert der `Domain`-Eigenschaft abzurufen.

   [!code-cpp[wrl-consume-component#8](../codesnippet/CPP/how-to-activate-and-use-a-windows-runtime-component-using-wrl_6.cpp)]

7. Drucken Sie den Domänennamen an die Konsole, und kehren Sie zurück. Alle `ComPtr`- und RAII-Objekte verlassen den Bereich und werden automatisch freigegeben.

   [!code-cpp[wrl-consume-component#9](../codesnippet/CPP/how-to-activate-and-use-a-windows-runtime-component-using-wrl_7.cpp)]

   Die [WindowsGetStringRawBuffer](/windows/desktop/api/winstring/nf-winstring-windowsgetstringrawbuffer) Funktion ruft das zugrunde liegende Unicode-Formular der URI-Zeichenfolge ab.

Im Folgenden sehen Sie das vollständige Beispiel:

[!code-cpp[wrl-consume-component#1](../codesnippet/CPP/how-to-activate-and-use-a-windows-runtime-component-using-wrl_8.cpp)]

## <a name="compiling-the-code"></a>Kompilieren des Codes

Um den Code zu kompilieren, kopieren Sie ihn und fügen Sie ihn in ein Visual Studio-Projekt ein, oder fügen Sie ihn in eine Datei mit dem Namen `wrl-consume-component.cpp` und führen Sie dann den folgenden Befehl in einem Fenster von Visual Studio-Eingabeaufforderung.

`cl.exe wrl-consume-component.cpp runtimeobject.lib`

## <a name="see-also"></a>Siehe auch

[Windows Runtime C++ Template Library (WRL)](windows-runtime-cpp-template-library-wrl.md)