# FindItem
$hWindow = WinGetHandle($TitleBBTSMain, "")      $hWnd = ControlGetHandle($hWindow, "", "[CLASS:TVirtualStringTree; INSTANCE:2]")     $iItemCnt = _GUICtrlTreeView_GetCount($hWnd)     ConsoleWrite("$iItemCnt  " &amp; $iItemCnt  &amp; @CRLF)      $searchText = "bs bp 1 -no restrictions"     $hItemFound = _GUICtrlTreeView_FindItem($hWnd, $searchText, True)     ConsoleWrite("$hItemFound " &amp; $hItemFound &amp; @CRLF)      While $hItemFound         _GUICtrlTreeView_SelectItem($hWnd, $hItemFound)         _GUICtrlTreeView_ClickItem($hWnd, $hItemFound)         $next = _GUICtrlTreeView_GetNextVisible($hWnd, $hItemFound)         $hItemFound = _GUICtrlTreeView_FindItem($hWnd, $searchText, True, $next)         Sleep(5000)     WEnd
