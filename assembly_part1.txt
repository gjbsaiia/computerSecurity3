00401000 >/$ 6A 00          PUSH 0                                   ; /pModule = NULL
00401002  |. E8 FF040000    CALL <JMP.&KERNEL32.GetModuleHandleA>    ; \GetModuleHandleA
00401007  |. A3 CA204000    MOV DWORD PTR DS:[4020CA],EAX
0040100C  |. 6A 00          PUSH 0                                   ; /Title = NULL
0040100E  |. 68 F4204000    PUSH CRACKME.004020F4                    ; |Class = "No need to disasm the code!"
00401013  |. E8 A6040000    CALL <JMP.&USER32.FindWindowA>           ; \FindWindowA
00401018  |. 0BC0           OR EAX,EAX
0040101A  |. 74 01          JE SHORT CRACKME.0040101D
0040101C  |. C3             RETN
0040101D  |> C705 64204000 >MOV DWORD PTR DS:[402064],4003
00401027  |. C705 68204000 >MOV DWORD PTR DS:[402068],CRACKME.WndPro>
00401031  |. C705 6C204000 >MOV DWORD PTR DS:[40206C],0
0040103B  |. C705 70204000 >MOV DWORD PTR DS:[402070],0
00401045  |. A1 CA204000    MOV EAX,DWORD PTR DS:[4020CA]
0040104A  |. A3 74204000    MOV DWORD PTR DS:[402074],EAX
0040104F  |. 6A 64          PUSH 64                                  ; /RsrcName = 100.
00401051  |. 50             PUSH EAX                                 ; |hInst => 00400000
00401052  |. E8 D1030000    CALL <JMP.&USER32.LoadIconA>             ; \LoadIconA
00401057  |. A3 78204000    MOV DWORD PTR DS:[402078],EAX
0040105C  |. 68 007F0000    PUSH 7F00                                ; /RsrcName = IDC_ARROW
00401061  |. 6A 00          PUSH 0                                   ; |hInst = NULL
00401063  |. E8 A2030000    CALL <JMP.&USER32.LoadCursorA>           ; \LoadCursorA
00401068  |. A3 7C204000    MOV DWORD PTR DS:[40207C],EAX
0040106D  |. C705 80204000 >MOV DWORD PTR DS:[402080],5
00401077  |. C705 84204000 >MOV DWORD PTR DS:[402084],CRACKME.004021>;  ASCII "MENU"
00401081  |. C705 88204000 >MOV DWORD PTR DS:[402088],CRACKME.004020>;  ASCII "No need to disasm the code!"
0040108B  |. 68 64204000    PUSH CRACKME.00402064                    ; /pWndClass = CRACKME.00402064
00401090  |. E8 F3030000    CALL <JMP.&USER32.RegisterClassA>        ; \RegisterClassA
00401095  |. 6A 00          PUSH 0                                   ; /lParam = NULL
00401097  |. FF35 CA204000  PUSH DWORD PTR DS:[4020CA]               ; |hInst = 00400000
0040109D  |. 6A 00          PUSH 0                                   ; |hMenu = NULL
0040109F  |. 6A 00          PUSH 0                                   ; |hParent = NULL
004010A1  |. 68 00800000    PUSH 8000                                ; |Height = 8000 (32768.)
004010A6  |. 68 00800000    PUSH 8000                                ; |Width = 8000 (32768.)
004010AB  |. 6A 6E          PUSH 6E                                  ; |Y = 6E (110.)
004010AD  |. 68 B4000000    PUSH 0B4                                 ; |X = B4 (180.)
004010B2  |. 68 0000CF00    PUSH 0CF0000                             ; |Style = WS_OVERLAPPED|WS_MINIMIZEBOX|WS_MAXIMIZEBOX|WS_SYSMENU|WS_THICKFRAME|WS_CAPTION
004010B7  |. 68 E7204000    PUSH CRACKME.004020E7                    ; |WindowName = "CrackMe v1.0"
004010BC  |. 68 F4204000    PUSH CRACKME.004020F4                    ; |Class = "No need to disasm the code!"
004010C1  |. 6A 00          PUSH 0                                   ; |ExtStyle = 0
004010C3  |. E8 CC030000    CALL <JMP.&USER32.CreateWindowExA>       ; \CreateWindowExA
004010C8  |. A3 04204000    MOV DWORD PTR DS:[402004],EAX
004010CD  |. 6A 01          PUSH 1                                   ; /ShowState = SW_SHOWNORMAL
004010CF  |. FF35 04204000  PUSH DWORD PTR DS:[402004]               ; |hWnd = 000807D0 ('CrackMe v1.0',class='No need to disasm the code!')
004010D5  |. E8 90030000    CALL <JMP.&USER32.ShowWindow>            ; \ShowWindow
004010DA  |. FF35 04204000  PUSH DWORD PTR DS:[402004]               ; /hWnd = 000807D0 ('CrackMe v1.0',class='No need to disasm the code!')
004010E0  |. E8 9D030000    CALL <JMP.&USER32.UpdateWindow>          ; \UpdateWindow
004010E5  |. 6A 01          PUSH 1                                   ; /Erase = TRUE
004010E7  |. 6A 00          PUSH 0                                   ; |pRect = NULL
004010E9  |. FF75 08        PUSH DWORD PTR SS:[EBP+8]                ; |hWnd
004010EC  |. E8 5B030000    CALL <JMP.&USER32.InvalidateRect>        ; \InvalidateRect
004010F1  |> 6A 00          /PUSH 0                                  ; /MsgFilterMax = 0
004010F3  |. 6A 00          |PUSH 0                                  ; |MsgFilterMin = 0
004010F5  |. 6A 00          |PUSH 0                                  ; |hWnd = NULL
004010F7  |. 68 48204000    |PUSH CRACKME.00402048                   ; |pMsg = CRACKME.00402048
004010FC  |. E8 D5030000    |CALL <JMP.&USER32.GetMessageA>          ; \GetMessageA
00401101  |. 66:3D 0000     |CMP AX,0
00401105  |. 74 16          |JE SHORT CRACKME.0040111D
00401107  |. 68 48204000    |PUSH CRACKME.00402048                   ; /pMsg = WM_TIMER hw = 5023C ("MSCTFIME UI") ID = 1 Callback = 0
0040110C  |. E8 4D030000    |CALL <JMP.&USER32.TranslateMessage>     ; \TranslateMessage
00401111  |. 68 48204000    |PUSH CRACKME.00402048                   ; /pMsg = WM_TIMER hw = 5023C ("MSCTFIME UI") ID = 1 Callback = 0
00401116  |. E8 8B030000    |CALL <JMP.&USER32.DispatchMessageA>     ; \DispatchMessageA
0040111B  |.^EB D4          \JMP SHORT CRACKME.004010F1
0040111D  |> FF35 50204000  PUSH DWORD PTR DS:[402050]               ; /ExitCode = 1
00401123  \. E8 EA030000    CALL <JMP.&KERNEL32.ExitProcess>         ; \ExitProcess
00401128 > $ C8 000000      ENTER 0,0
0040112C   . 56             PUSH ESI
0040112D   . 57             PUSH EDI
0040112E   . 53             PUSH EBX
0040112F   . 837D 0C 02     CMP DWORD PTR SS:[EBP+C],2
00401133   . 74 5E          JE SHORT CRACKME.00401193
00401135   . 817D 0C 040200>CMP DWORD PTR SS:[EBP+C],204
0040113C   . 74 65          JE SHORT CRACKME.004011A3
0040113E   . 90             NOP
0040113F   . 90             NOP
00401140   . 90             NOP
00401141   . 90             NOP
00401142   . 837D 0C 05     CMP DWORD PTR SS:[EBP+C],5
00401146   . 74 5D          JE SHORT CRACKME.004011A5
00401148   . 837D 0C 01     CMP DWORD PTR SS:[EBP+C],1
0040114C   . 74 28          JE SHORT CRACKME.00401176
0040114E   . 817D 0C 010200>CMP DWORD PTR SS:[EBP+C],201
00401155   . 74 4A          JE SHORT CRACKME.004011A1
00401157   . 837D 0C 24     CMP DWORD PTR SS:[EBP+C],24
0040115B   . 74 4F          JE SHORT CRACKME.004011AC
0040115D   . 817D 0C 110100>CMP DWORD PTR SS:[EBP+C],111
00401164   . 74 6C          JE SHORT CRACKME.004011D2
00401166   . 90             NOP
00401167   . 90             NOP
00401168   . 90             NOP
00401169   . 90             NOP
0040116A   . EB 14          JMP SHORT CRACKME.00401180
0040116C   . B8 00000000    MOV EAX,0
00401171   . EB 73          JMP SHORT CRACKME.004011E6
00401173     90             NOP
00401174     90             NOP
00401175     90             NOP
00401176   > B8 00000000    MOV EAX,0
0040117B   . EB 69          JMP SHORT CRACKME.004011E6
0040117D     90             NOP
0040117E     90             NOP
0040117F     90             NOP
00401180   > FF75 14        PUSH DWORD PTR SS:[EBP+14]               ; /lParam
00401183   . FF75 10        PUSH DWORD PTR SS:[EBP+10]               ; |wParam
00401186   . FF75 0C        PUSH DWORD PTR SS:[EBP+C]                ; |Message
00401189   . FF75 08        PUSH DWORD PTR SS:[EBP+8]                ; |hWnd
0040118C   . E8 09030000    CALL <JMP.&USER32.DefWindowProcA>        ; \DefWindowProcA
00401191   . EB 53          JMP SHORT CRACKME.004011E6
00401193   > 6A 00          PUSH 0                                   ; /ExitCode = 0
00401195   . E8 A6020000    CALL <JMP.&USER32.PostQuitMessage>       ; \PostQuitMessage
0040119A   . B8 00000000    MOV EAX,0
0040119F   . EB 45          JMP SHORT CRACKME.004011E6
004011A1   > EB 43          JMP SHORT CRACKME.004011E6
004011A3   > EB 41          JMP SHORT CRACKME.004011E6
004011A5   > B8 00000000    MOV EAX,0
004011AA   . EB 3A          JMP SHORT CRACKME.004011E6
004011AC   > 8B5D 14        MOV EBX,DWORD PTR SS:[EBP+14]
004011AF   . C743 18 180100>MOV DWORD PTR DS:[EBX+18],118
004011B6   . C743 1C A00000>MOV DWORD PTR DS:[EBX+1C],0A0
004011BD   . C743 20 180100>MOV DWORD PTR DS:[EBX+20],118
004011C4   . C743 24 A00000>MOV DWORD PTR DS:[EBX+24],0A0
004011CB   . B8 00000000    MOV EAX,0
004011D0   . EB 14          JMP SHORT CRACKME.004011E6
004011D2   > 837D 10 67     CMP DWORD PTR SS:[EBP+10],67
004011D6   . 74 15          JE SHORT CRACKME.004011ED
004011D8   . 837D 10 65     CMP DWORD PTR SS:[EBP+10],65
004011DC   .^74 B5          JE SHORT CRACKME.00401193
004011DE   . 837D 10 66     CMP DWORD PTR SS:[EBP+10],66
004011E2   . 74 25          JE SHORT CRACKME.00401209
004011E4   . EB 00          JMP SHORT CRACKME.004011E6
004011E6   > 5B             POP EBX
004011E7   . 5F             POP EDI
004011E8   . 5E             POP ESI
004011E9   . C9             LEAVE
004011EA   . C2 1000        RETN 10
004011ED   > 6A 00          PUSH 0                                   ; /lParam = NULL
004011EF   . 68 0A134000    PUSH CRACKME.0040130A                    ; |DlgProc = CRACKME.0040130A
004011F4   . FF75 08        PUSH DWORD PTR SS:[EBP+8]                ; |hOwner
004011F7   . 68 1F214000    PUSH CRACKME.0040211F                    ; |pTemplate = "DLG_ABOUT"
004011FC   . FF35 CA204000  PUSH DWORD PTR DS:[4020CA]               ; |hInst = 00400000
00401202   . E8 99020000    CALL <JMP.&USER32.DialogBoxParamA>       ; \DialogBoxParamA
00401207   .^EB DD          JMP SHORT CRACKME.004011E6
00401209   > 6A 00          PUSH 0                                   ; /lParam = NULL
0040120B   . 68 53124000    PUSH CRACKME.00401253                    ; |DlgProc = CRACKME.00401253
00401210   . FF75 08        PUSH DWORD PTR SS:[EBP+8]                ; |hOwner
00401213   . 68 15214000    PUSH CRACKME.00402115                    ; |pTemplate = "DLG_REGIS"
00401218   . FF35 CA204000  PUSH DWORD PTR DS:[4020CA]               ; |hInst = 00400000
0040121E   . E8 7D020000    CALL <JMP.&USER32.DialogBoxParamA>       ; \DialogBoxParamA
00401223   . 83F8 00        CMP EAX,0
00401226   .^74 BE          JE SHORT CRACKME.004011E6
00401228   . 68 8E214000    PUSH CRACKME.0040218E
0040122D   . E8 4C010000    CALL CRACKME.0040137E
00401232   . 50             PUSH EAX
00401233   . 68 7E214000    PUSH CRACKME.0040217E
00401238   . E8 9B010000    CALL CRACKME.004013D8
0040123D   . 83C4 04        ADD ESP,4
00401240   . 58             POP EAX
00401241   . 3BC3           CMP EAX,EAX
00401243   . 74 07          JE SHORT CRACKME.0040124C
00401245   . E8 18010000    CALL CRACKME.00401362
0040124A   .^EB 9A          JMP SHORT CRACKME.004011E6
0040124C   > E8 FC000000    CALL CRACKME.0040134D
00401251   .^EB 93          JMP SHORT CRACKME.004011E6
00401253  /. C8 000000      ENTER 0,0
00401257  |. 53             PUSH EBX
00401258  |. 56             PUSH ESI
00401259  |. 57             PUSH EDI
0040125A  |. 817D 0C 100100>CMP DWORD PTR SS:[EBP+C],110
00401261  |. 74 34          JE SHORT CRACKME.00401297
00401263  |. 817D 0C 110100>CMP DWORD PTR SS:[EBP+C],111
0040126A  |. 74 35          JE SHORT CRACKME.004012A1
0040126C  |. 837D 0C 10     CMP DWORD PTR SS:[EBP+C],10
00401270  |. 0F84 81000000  JE CRACKME.004012F7
00401276  |. 817D 0C 010200>CMP DWORD PTR SS:[EBP+C],201
0040127D  |. 74 0C          JE SHORT CRACKME.0040128B
0040127F  |. B8 00000000    MOV EAX,0
00401284  |> 5F             POP EDI
00401285  |. 5E             POP ESI
00401286  |. 5B             POP EBX
00401287  |. C9             LEAVE
00401288  |. C2 1000        RETN 10
0040128B  |> 6A 01          PUSH 1                                   ; /Erase = TRUE
0040128D  |. 6A 00          PUSH 0                                   ; |pRect = NULL
0040128F  |. FF75 08        PUSH DWORD PTR SS:[EBP+8]                ; |hWnd
00401292  |. E8 B5010000    CALL <JMP.&USER32.InvalidateRect>        ; \InvalidateRect
00401297  |> FF75 08        PUSH DWORD PTR SS:[EBP+8]                ; /hWnd
0040129A  |. E8 95010000    CALL <JMP.&USER32.SetFocus>              ; \SetFocus
0040129F  |.^EB E3          JMP SHORT CRACKME.00401284
004012A1  |> 33C0           /XOR EAX,EAX
004012A3  |. 817D 10 EB0300>|CMP DWORD PTR SS:[EBP+10],3EB
004012AA  |. 74 4B          |JE SHORT CRACKME.004012F7
004012AC  |. 817D 10 EA0300>|CMP DWORD PTR SS:[EBP+10],3EA
004012B3  |. 75 3B          |JNZ SHORT CRACKME.004012F0
004012B5  |. 6A 0B          |PUSH 0B                                 ; /Count = B (11.)
004012B7  |. 68 8E214000    |PUSH CRACKME.0040218E                   ; |Buffer = CRACKME.0040218E
004012BC  |. 68 E8030000    |PUSH 3E8                                ; |ControlID = 3E8 (1000.)
004012C1  |. FF75 08        |PUSH DWORD PTR SS:[EBP+8]               ; |hWnd
004012C4  |. E8 07020000    |CALL <JMP.&USER32.GetDlgItemTextA>      ; \GetDlgItemTextA
004012C9  |. 83F8 01        |CMP EAX,1
004012CC  |. C745 10 EB0300>|MOV DWORD PTR SS:[EBP+10],3EB
004012D3  |.^72 CC          \JB SHORT CRACKME.004012A1
004012D5  |. 6A 0B          PUSH 0B                                  ; /Count = B (11.)
004012D7  |. 68 7E214000    PUSH CRACKME.0040217E                    ; |Buffer = CRACKME.0040217E
004012DC  |. 68 E9030000    PUSH 3E9                                 ; |ControlID = 3E9 (1001.)
004012E1  |. FF75 08        PUSH DWORD PTR SS:[EBP+8]                ; |hWnd
004012E4  |. E8 E7010000    CALL <JMP.&USER32.GetDlgItemTextA>       ; \GetDlgItemTextA
004012E9  |. B8 01000000    MOV EAX,1
004012EE  |. EB 07          JMP SHORT CRACKME.004012F7
004012F0  |> B8 00000000    MOV EAX,0
004012F5  |.^EB 8D          JMP SHORT CRACKME.00401284
004012F7  |> 50             PUSH EAX                                 ; /Result
004012F8  |. FF75 08        PUSH DWORD PTR SS:[EBP+8]                ; |hWnd
004012FB  |. E8 B2010000    CALL <JMP.&USER32.EndDialog>             ; \EndDialog
00401300  |. B8 01000000    MOV EAX,1
00401305  \.^E9 7AFFFFFF    JMP CRACKME.00401284
0040130A  /. C8 000000      ENTER 0,0
0040130E  |. 53             PUSH EBX
0040130F  |. 56             PUSH ESI
00401310  |. 57             PUSH EDI
00401311  |. 817D 0C 110100>CMP DWORD PTR SS:[EBP+C],111
00401318  |. 74 12          JE SHORT CRACKME.0040132C
0040131A  |. 837D 0C 10     CMP DWORD PTR SS:[EBP+C],10
0040131E  |. 74 15          JE SHORT CRACKME.00401335
00401320  |. B8 00000000    MOV EAX,0
00401325  |> 5F             POP EDI
00401326  |. 5E             POP ESI
00401327  |. 5B             POP EBX
00401328  |. C9             LEAVE
00401329  |. C2 1000        RETN 10
0040132C  |> 817D 10 F20300>CMP DWORD PTR SS:[EBP+10],3F2
00401333  |. 75 11          JNZ SHORT CRACKME.00401346
00401335  |> 6A 00          PUSH 0                                   ; /Result = 0
00401337  |. FF75 08        PUSH DWORD PTR SS:[EBP+8]                ; |hWnd
0040133A  |. E8 73010000    CALL <JMP.&USER32.EndDialog>             ; \EndDialog
0040133F  |. B8 01000000    MOV EAX,1
00401344  |.^EB DF          JMP SHORT CRACKME.00401325
00401346  |> B8 00000000    MOV EAX,0
0040134B  \.^EB D8          JMP SHORT CRACKME.00401325
0040134D  /$ 6A 30          PUSH 30                                  ; /Style = MB_OK|MB_ICONEXCLAMATION|MB_APPLMODAL
0040134F  |. 68 29214000    PUSH CRACKME.00402129                    ; |Title = "Good work!"
00401354  |. 68 34214000    PUSH CRACKME.00402134                    ; |Text = "Great work, mate!
Now try the next CrackMe!"
00401359  |. FF75 08        PUSH DWORD PTR SS:[EBP+8]                ; |hOwner
0040135C  |. E8 D9000000    CALL <JMP.&USER32.MessageBoxA>           ; \MessageBoxA
00401361  \. C3             RETN
00401362  /$ 6A 00          PUSH 0                                   ; /BeepType = MB_OK
00401364  |. E8 AD000000    CALL <JMP.&USER32.MessageBeep>           ; \MessageBeep
00401369  |. 6A 30          PUSH 30                                  ; /Style = MB_OK|MB_ICONEXCLAMATION|MB_APPLMODAL
0040136B  |. 68 60214000    PUSH CRACKME.00402160                    ; |Title = "No luck!"
00401370  |. 68 69214000    PUSH CRACKME.00402169                    ; |Text = "No luck there, mate!"
00401375  |. FF75 08        PUSH DWORD PTR SS:[EBP+8]                ; |hOwner
00401378  |. E8 BD000000    CALL <JMP.&USER32.MessageBoxA>           ; \MessageBoxA
0040137D  \. C3             RETN
0040137E  /$ 8B7424 04      MOV ESI,DWORD PTR SS:[ESP+4]
00401382  |. 56             PUSH ESI
00401383  |> 8A06           /MOV AL,BYTE PTR DS:[ESI]
00401385  |. 84C0           |TEST AL,AL
00401387  |. 74 13          |JE SHORT CRACKME.0040139C
00401389  |. 3C 41          |CMP AL,41
0040138B  |. 72 1F          |JB SHORT CRACKME.004013AC
0040138D  |. 3C 5A          |CMP AL,5A
0040138F  |. 73 03          |JNB SHORT CRACKME.00401394
00401391  |. 46             |INC ESI
00401392  |.^EB EF          |JMP SHORT CRACKME.00401383
00401394  |> E8 39000000    |CALL CRACKME.004013D2
00401399  |. 46             |INC ESI
0040139A  |.^EB E7          \JMP SHORT CRACKME.00401383
0040139C  |> 5E             POP ESI
0040139D  |. E8 20000000    CALL CRACKME.004013C2
004013A2  |. 81F7 78560000  XOR EDI,5678
004013A8  |. 8BC7           MOV EAX,EDI
004013AA  |. EB 15          JMP SHORT CRACKME.004013C1
004013AC  |> 5E             POP ESI
004013AD  |. 6A 30          PUSH 30                                  ; /Style = MB_OK|MB_ICONEXCLAMATION|MB_APPLMODAL
004013AF  |. 68 60214000    PUSH CRACKME.00402160                    ; |Title = "No luck!"
004013B4  |. 68 69214000    PUSH CRACKME.00402169                    ; |Text = "No luck there, mate!"
004013B9  |. FF75 08        PUSH DWORD PTR SS:[EBP+8]                ; |hOwner
004013BC  |. E8 79000000    CALL <JMP.&USER32.MessageBoxA>           ; \MessageBoxA
004013C1  \> C3             RETN
004013C2  /$ 33FF           XOR EDI,EDI
004013C4  |. 33DB           XOR EBX,EBX
004013C6  |> 8A1E           /MOV BL,BYTE PTR DS:[ESI]
004013C8  |. 84DB           |TEST BL,BL
004013CA  |. 74 05          |JE SHORT CRACKME.004013D1
004013CC  |. 03FB           |ADD EDI,EBX
004013CE  |. 46             |INC ESI
004013CF  |.^EB F5          \JMP SHORT CRACKME.004013C6
004013D1  \> C3             RETN
004013D2  /$ 2C 20          SUB AL,20
004013D4  |. 8806           MOV BYTE PTR DS:[ESI],AL
004013D6  \. C3             RETN
004013D7   . C3             RETN
004013D8  /$ 33C0           XOR EAX,EAX
004013DA  |. 33FF           XOR EDI,EDI
004013DC  |. 33DB           XOR EBX,EBX
004013DE  |. 8B7424 04      MOV ESI,DWORD PTR SS:[ESP+4]
004013E2  |> B0 0A          /MOV AL,0A
004013E4  |. 8A1E           |MOV BL,BYTE PTR DS:[ESI]
004013E6  |. 84DB           |TEST BL,BL
004013E8  |. 74 0B          |JE SHORT CRACKME.004013F5
004013EA  |. 80EB 30        |SUB BL,30
004013ED  |. 0FAFF8         |IMUL EDI,EAX
004013F0  |. 03FB           |ADD EDI,EBX
004013F2  |. 46             |INC ESI
004013F3  |.^EB ED          \JMP SHORT CRACKME.004013E2
004013F5  |> 81F7 34120000  XOR EDI,1234
004013FB  |. 8BDF           MOV EBX,EDI
004013FD  \. C3             RETN
004013FE   .-FF25 84314000  JMP DWORD PTR DS:[<&USER32.KillTimer>]   ;  USER32.KillTimer
00401404   .-FF25 88314000  JMP DWORD PTR DS:[<&USER32.GetSystemMetr>;  USER32.GetSystemMetrics
0040140A   $-FF25 8C314000  JMP DWORD PTR DS:[<&USER32.LoadCursorA>] ;  USER32.LoadCursorA
00401410   .-FF25 90314000  JMP DWORD PTR DS:[<&USER32.LoadAccelerat>;  USER32.LoadAcceleratorsA
00401416   $-FF25 94314000  JMP DWORD PTR DS:[<&USER32.MessageBeep>] ;  USER32.MessageBeep
0040141C   .-FF25 98314000  JMP DWORD PTR DS:[<&USER32.GetWindowRect>;  USER32.GetWindowRect
00401422   .-FF25 9C314000  JMP DWORD PTR DS:[<&USER32.LoadStringA>] ;  USER32.LoadStringA
00401428   $-FF25 A0314000  JMP DWORD PTR DS:[<&USER32.LoadIconA>]   ;  USER32.LoadIconA
0040142E   .-FF25 A4314000  JMP DWORD PTR DS:[<&USER32.LoadBitmapA>] ;  USER32.LoadBitmapA
00401434   $-FF25 A8314000  JMP DWORD PTR DS:[<&USER32.SetFocus>]    ;  USER32.SetFocus
0040143A   $-FF25 AC314000  JMP DWORD PTR DS:[<&USER32.MessageBoxA>] ;  USER32.MessageBoxA
00401440   $-FF25 B0314000  JMP DWORD PTR DS:[<&USER32.PostQuitMessa>;  USER32.PostQuitMessage
00401446   .-FF25 B4314000  JMP DWORD PTR DS:[<&USER32.WinHelpA>]    ;  USER32.WinHelpA
0040144C   $-FF25 B8314000  JMP DWORD PTR DS:[<&USER32.InvalidateRec>;  USER32.InvalidateRect
00401452   .-FF25 BC314000  JMP DWORD PTR DS:[<&USER32.TranslateAcce>;  USER32.TranslateAcceleratorA
00401458   .-FF25 C0314000  JMP DWORD PTR DS:[<&USER32.MoveWindow>]  ;  USER32.MoveWindow
0040145E   $-FF25 C4314000  JMP DWORD PTR DS:[<&USER32.TranslateMess>;  USER32.TranslateMessage
00401464   .-FF25 C8314000  JMP DWORD PTR DS:[<&USER32.LoadMenuA>]   ;  USER32.LoadMenuA
0040146A   $-FF25 CC314000  JMP DWORD PTR DS:[<&USER32.ShowWindow>]  ;  USER32.ShowWindow
00401470   .-FF25 D0314000  JMP DWORD PTR DS:[<&USER32.SendMessageA>>;  USER32.SendMessageA
00401476   .-FF25 D4314000  JMP DWORD PTR DS:[<&USER32.SetTimer>]    ;  USER32.SetTimer
0040147C   .-FF25 D8314000  JMP DWORD PTR DS:[<&USER32.SetWindowPos>>;  USER32.SetWindowPos
00401482   $-FF25 DC314000  JMP DWORD PTR DS:[<&USER32.UpdateWindow>>;  USER32.UpdateWindow
00401488   $-FF25 E0314000  JMP DWORD PTR DS:[<&USER32.RegisterClass>;  USER32.RegisterClassA
0040148E   .-FF25 E4314000  JMP DWORD PTR DS:[<&USER32.BeginPaint>]  ;  USER32.BeginPaint
00401494   $-FF25 E8314000  JMP DWORD PTR DS:[<&USER32.CreateWindowE>;  USER32.CreateWindowExA
0040149A   $-FF25 EC314000  JMP DWORD PTR DS:[<&USER32.DefWindowProc>;  ntdll.NtdllDefWindowProc_A
004014A0   $-FF25 F0314000  JMP DWORD PTR DS:[<&USER32.DialogBoxPara>;  USER32.DialogBoxParamA
004014A6   $-FF25 F4314000  JMP DWORD PTR DS:[<&USER32.DispatchMessa>;  USER32.DispatchMessageA
004014AC   .-FF25 F8314000  JMP DWORD PTR DS:[<&USER32.DrawMenuBar>] ;  USER32.DrawMenuBar
004014B2   $-FF25 FC314000  JMP DWORD PTR DS:[<&USER32.EndDialog>]   ;  USER32.EndDialog
004014B8   .-FF25 00324000  JMP DWORD PTR DS:[<&USER32.EndPaint>]    ;  USER32.EndPaint
004014BE   $-FF25 04324000  JMP DWORD PTR DS:[<&USER32.FindWindowA>] ;  USER32.FindWindowA
004014C4   .-FF25 08324000  JMP DWORD PTR DS:[<&USER32.GetDC>]       ;  USER32.GetDC
004014CA   .-FF25 0C324000  JMP DWORD PTR DS:[<&USER32.GetDlgItem>]  ;  USER32.GetDlgItem
004014D0   $-FF25 10324000  JMP DWORD PTR DS:[<&USER32.GetDlgItemTex>;  USER32.GetDlgItemTextA
004014D6   $-FF25 14324000  JMP DWORD PTR DS:[<&USER32.GetMessageA>] ;  USER32.GetMessageA
004014DC   .-FF25 1C324000  JMP DWORD PTR DS:[<&KERNEL32.GetLocalTim>;  KERNEL32.GetLocalTime
004014E2   .-FF25 20324000  JMP DWORD PTR DS:[<&KERNEL32.OpenFile>]  ;  KERNEL32.OpenFile
004014E8   .-FF25 24324000  JMP DWORD PTR DS:[<&KERNEL32.GlobalFree>>;  KERNEL32.GlobalFree
004014EE   .-FF25 28324000  JMP DWORD PTR DS:[<&KERNEL32.GlobalAlloc>;  KERNEL32.GlobalAlloc
004014F4   .-FF25 2C324000  JMP DWORD PTR DS:[<&KERNEL32.lstrlen>]   ;  KERNEL32.lstrlenA
004014FA   .-FF25 30324000  JMP DWORD PTR DS:[<&KERNEL32.CloseHandle>;  KERNEL32.CloseHandle
00401500   .-FF25 34324000  JMP DWORD PTR DS:[<&KERNEL32.WriteFile>] ;  KERNEL32.WriteFile
00401506   $-FF25 38324000  JMP DWORD PTR DS:[<&KERNEL32.GetModuleHa>;  KERNEL32.GetModuleHandleA
0040150C   .-FF25 3C324000  JMP DWORD PTR DS:[<&KERNEL32.ReadFile>]  ;  KERNEL32.ReadFile
00401512   .-FF25 40324000  JMP DWORD PTR DS:[<&KERNEL32.ExitProcess>;  KERNEL32.ExitProcess
00401518   .-FF25 48324000  JMP DWORD PTR DS:[<&COMCTL32.InitCommonC>;  COMCTL32.InitCommonControls
0040151E   .-FF25 4C324000  JMP DWORD PTR DS:[<&COMCTL32.CreateToolb>;  COMCTL32.CreateToolbarEx
00401524   .-FF25 50324000  JMP DWORD PTR DS:[<&COMCTL32.CreateToolb>;  COMCTL32.CreateToolbar
0040152A   .-FF25 58324000  JMP DWORD PTR DS:[<&GDI32.TextOutA>]     ;  GDI32.TextOutA
00401530   .-FF25 5C324000  JMP DWORD PTR DS:[<&GDI32.StartPage>]    ;  GDI32.StartPage
00401536   .-FF25 60324000  JMP DWORD PTR DS:[<&GDI32.StartDocA>]    ;  GDI32.StartDocA
0040153C   .-FF25 64324000  JMP DWORD PTR DS:[<&GDI32.GetTextMetrics>;  GDI32.GetTextMetricsA
00401542   .-FF25 68324000  JMP DWORD PTR DS:[<&GDI32.GetStockObject>;  GDI32.GetStockObject
00401548   .-FF25 6C324000  JMP DWORD PTR DS:[<&GDI32.EndPage>]      ;  GDI32.EndPage
0040154E   .-FF25 70324000  JMP DWORD PTR DS:[<&GDI32.EndDoc>]       ;  GDI32.EndDoc
00401554   .-FF25 74324000  JMP DWORD PTR DS:[<&GDI32.DeleteObject>] ;  GDI32.DeleteObject
0040155A   .-FF25 78324000  JMP DWORD PTR DS:[<&GDI32.DeleteDC>]     ;  GDI32.DeleteDC
00401560   .-FF25 80324000  JMP DWORD PTR DS:[<&COMDLG32.GetSaveFile>;  COMDLG32.GetSaveFileNameA
00401566   .-FF25 84324000  JMP DWORD PTR DS:[<&COMDLG32.GetOpenFile>;  COMDLG32.GetOpenFileNameA
0040156C   .-FF25 88324000  JMP DWORD PTR DS:[<&COMDLG32.PrintDlgA>] ;  COMDLG32.PrintDlgA
00401572     00             DB 00
00401573     00             DB 00
00401574     00             DB 00
00401575     00             DB 00
00401576     00             DB 00
00401577     00             DB 00
00401578     00             DB 00
00401579     00             DB 00
0040157A     00             DB 00
0040157B     00             DB 00
0040157C     00             DB 00
0040157D     00             DB 00
0040157E     00             DB 00
0040157F     00             DB 00
00401580     00             DB 00
00401581     00             DB 00
00401582     00             DB 00
00401583     00             DB 00
00401584     00             DB 00
00401585     00             DB 00
00401586     00             DB 00
00401587     00             DB 00
00401588     00             DB 00
00401589     00             DB 00
0040158A     00             DB 00
0040158B     00             DB 00
0040158C     00             DB 00
0040158D     00             DB 00
0040158E     00             DB 00
0040158F     00             DB 00
00401590     00             DB 00
00401591     00             DB 00
00401592     00             DB 00
00401593     00             DB 00
00401594     00             DB 00
00401595     00             DB 00
00401596     00             DB 00
00401597     00             DB 00
00401598     00             DB 00
00401599     00             DB 00
0040159A     00             DB 00
0040159B     00             DB 00
0040159C     00             DB 00
0040159D     00             DB 00
0040159E     00             DB 00
0040159F     00             DB 00
004015A0     00             DB 00
004015A1     00             DB 00
004015A2     00             DB 00
004015A3     00             DB 00
004015A4     00             DB 00
004015A5     00             DB 00
004015A6     00             DB 00
004015A7     00             DB 00
004015A8     00             DB 00
004015A9     00             DB 00
004015AA     00             DB 00
004015AB     00             DB 00
004015AC     00             DB 00
004015AD     00             DB 00
004015AE     00             DB 00
004015AF     00             DB 00
004015B0     00             DB 00
004015B1     00             DB 00
004015B2     00             DB 00
004015B3     00             DB 00
004015B4     00             DB 00
004015B5     00             DB 00
004015B6     00             DB 00
004015B7     00             DB 00
004015B8     00             DB 00
004015B9     00             DB 00
004015BA     00             DB 00
004015BB     00             DB 00
004015BC     00             DB 00
004015BD     00             DB 00
004015BE     00             DB 00
004015BF     00             DB 00
004015C0     00             DB 00
004015C1     00             DB 00
004015C2     00             DB 00
004015C3     00             DB 00
004015C4     00             DB 00
004015C5     00             DB 00
004015C6     00             DB 00
004015C7     00             DB 00
004015C8     00             DB 00
004015C9     00             DB 00
004015CA     00             DB 00
004015CB     00             DB 00
004015CC     00             DB 00
004015CD     00             DB 00
004015CE     00             DB 00
004015CF     00             DB 00
004015D0     00             DB 00
004015D1     00             DB 00
004015D2     00             DB 00
004015D3     00             DB 00
004015D4     00             DB 00
004015D5     00             DB 00
004015D6     00             DB 00
004015D7     00             DB 00
004015D8     00             DB 00
004015D9     00             DB 00
004015DA     00             DB 00
004015DB     00             DB 00
004015DC     00             DB 00
004015DD     00             DB 00
004015DE     00             DB 00
004015DF     00             DB 00
004015E0     00             DB 00
004015E1     00             DB 00
004015E2     00             DB 00
004015E3     00             DB 00
004015E4     00             DB 00
004015E5     00             DB 00
004015E6     00             DB 00
004015E7     00             DB 00
004015E8     00             DB 00
004015E9     00             DB 00
004015EA     00             DB 00
004015EB     00             DB 00
004015EC     00             DB 00
004015ED     00             DB 00
004015EE     00             DB 00
004015EF     00             DB 00
004015F0     00             DB 00
004015F1     00             DB 00
004015F2     00             DB 00
004015F3     00             DB 00
004015F4     00             DB 00
004015F5     00             DB 00
004015F6     00             DB 00
004015F7     00             DB 00
004015F8     00             DB 00
004015F9     00             DB 00
004015FA     00             DB 00
004015FB     00             DB 00
004015FC     00             DB 00
004015FD     00             DB 00
004015FE     00             DB 00
004015FF     00             DB 00
00401600     00             DB 00
00401601     00             DB 00
00401602     00             DB 00
00401603     00             DB 00
00401604     00             DB 00
00401605     00             DB 00
00401606     00             DB 00
00401607     00             DB 00
00401608     00             DB 00
00401609     00             DB 00
0040160A     00             DB 00
0040160B     00             DB 00
0040160C     00             DB 00
0040160D     00             DB 00
0040160E     00             DB 00
0040160F     00             DB 00
00401610     00             DB 00
00401611     00             DB 00
00401612     00             DB 00
00401613     00             DB 00
00401614     00             DB 00
00401615     00             DB 00
00401616     00             DB 00
00401617     00             DB 00
00401618     00             DB 00
00401619     00             DB 00
0040161A     00             DB 00
0040161B     00             DB 00
0040161C     00             DB 00
0040161D     00             DB 00
0040161E     00             DB 00
0040161F     00             DB 00
00401620     00             DB 00
00401621     00             DB 00
00401622     00             DB 00
00401623     00             DB 00
00401624     00             DB 00
00401625     00             DB 00
00401626     00             DB 00
00401627     00             DB 00
00401628     00             DB 00
00401629     00             DB 00
0040162A     00             DB 00
0040162B     00             DB 00
0040162C     00             DB 00
0040162D     00             DB 00
0040162E     00             DB 00
0040162F     00             DB 00
00401630     00             DB 00
00401631     00             DB 00
00401632     00             DB 00
00401633     00             DB 00
00401634     00             DB 00
00401635     00             DB 00
00401636     00             DB 00
00401637     00             DB 00
00401638     00             DB 00
00401639     00             DB 00
0040163A     00             DB 00
0040163B     00             DB 00
0040163C     00             DB 00
0040163D     00             DB 00
0040163E     00             DB 00
0040163F     00             DB 00
00401640     00             DB 00
00401641     00             DB 00
00401642     00             DB 00
00401643     00             DB 00
00401644     00             DB 00
00401645     00             DB 00
00401646     00             DB 00
00401647     00             DB 00
00401648     00             DB 00
00401649     00             DB 00
0040164A     00             DB 00
0040164B     00             DB 00
0040164C     00             DB 00
0040164D     00             DB 00
0040164E     00             DB 00
0040164F     00             DB 00
00401650     00             DB 00
00401651     00             DB 00
00401652     00             DB 00
00401653     00             DB 00
00401654     00             DB 00
00401655     00             DB 00
00401656     00             DB 00
00401657     00             DB 00
00401658     00             DB 00
00401659     00             DB 00
0040165A     00             DB 00
0040165B     00             DB 00
0040165C     00             DB 00
0040165D     00             DB 00
0040165E     00             DB 00
0040165F     00             DB 00
00401660     00             DB 00
00401661     00             DB 00
00401662     00             DB 00
00401663     00             DB 00
00401664     00             DB 00
00401665     00             DB 00
00401666     00             DB 00
00401667     00             DB 00
00401668     00             DB 00
00401669     00             DB 00
0040166A     00             DB 00
0040166B     00             DB 00
0040166C     00             DB 00
0040166D     00             DB 00
0040166E     00             DB 00
0040166F     00             DB 00
00401670     00             DB 00
00401671     00             DB 00
00401672     00             DB 00
00401673     00             DB 00
00401674     00             DB 00
00401675     00             DB 00
00401676     00             DB 00
00401677     00             DB 00
00401678     00             DB 00
00401679     00             DB 00
0040167A     00             DB 00
0040167B     00             DB 00
0040167C     00             DB 00
0040167D     00             DB 00
0040167E     00             DB 00
0040167F     00             DB 00
00401680     00             DB 00
00401681     00             DB 00
00401682     00             DB 00
00401683     00             DB 00
00401684     00             DB 00
00401685     00             DB 00
00401686     00             DB 00
00401687     00             DB 00
00401688     00             DB 00
00401689     00             DB 00
0040168A     00             DB 00
0040168B     00             DB 00
0040168C     00             DB 00
0040168D     00             DB 00
0040168E     00             DB 00
0040168F     00             DB 00
00401690     00             DB 00
00401691     00             DB 00
00401692     00             DB 00
00401693     00             DB 00
00401694     00             DB 00
00401695     00             DB 00
00401696     00             DB 00
00401697     00             DB 00
00401698     00             DB 00
00401699     00             DB 00
0040169A     00             DB 00
0040169B     00             DB 00
0040169C     00             DB 00
0040169D     00             DB 00
0040169E     00             DB 00
0040169F     00             DB 00
004016A0     00             DB 00
004016A1     00             DB 00
004016A2     00             DB 00
004016A3     00             DB 00
004016A4     00             DB 00
004016A5     00             DB 00
004016A6     00             DB 00
004016A7     00             DB 00
004016A8     00             DB 00
004016A9     00             DB 00
004016AA     00             DB 00
004016AB     00             DB 00
004016AC     00             DB 00
004016AD     00             DB 00
004016AE     00             DB 00
004016AF     00             DB 00
004016B0     00             DB 00
004016B1     00             DB 00
004016B2     00             DB 00
004016B3     00             DB 00
004016B4     00             DB 00
004016B5     00             DB 00
004016B6     00             DB 00
004016B7     00             DB 00
004016B8     00             DB 00
004016B9     00             DB 00
004016BA     00             DB 00
004016BB     00             DB 00
004016BC     00             DB 00
004016BD     00             DB 00
004016BE     00             DB 00
004016BF     00             DB 00
004016C0     00             DB 00
004016C1     00             DB 00
004016C2     00             DB 00
004016C3     00             DB 00
004016C4     00             DB 00
004016C5     00             DB 00
004016C6     00             DB 00
004016C7     00             DB 00
004016C8     00             DB 00
004016C9     00             DB 00
004016CA     00             DB 00
004016CB     00             DB 00
004016CC     00             DB 00
004016CD     00             DB 00
004016CE     00             DB 00
004016CF     00             DB 00
004016D0     00             DB 00
004016D1     00             DB 00
004016D2     00             DB 00
004016D3     00             DB 00
004016D4     00             DB 00
004016D5     00             DB 00
004016D6     00             DB 00
004016D7     00             DB 00
004016D8     00             DB 00
004016D9     00             DB 00
004016DA     00             DB 00
004016DB     00             DB 00
004016DC     00             DB 00
004016DD     00             DB 00
004016DE     00             DB 00
004016DF     00             DB 00
004016E0     00             DB 00
004016E1     00             DB 00
004016E2     00             DB 00
004016E3     00             DB 00
004016E4     00             DB 00
004016E5     00             DB 00
004016E6     00             DB 00
004016E7     00             DB 00
004016E8     00             DB 00
004016E9     00             DB 00
004016EA     00             DB 00
004016EB     00             DB 00
004016EC     00             DB 00
004016ED     00             DB 00
004016EE     00             DB 00
004016EF     00             DB 00
004016F0     00             DB 00
004016F1     00             DB 00
004016F2     00             DB 00
004016F3     00             DB 00
004016F4     00             DB 00
004016F5     00             DB 00
004016F6     00             DB 00
004016F7     00             DB 00
004016F8     00             DB 00
004016F9     00             DB 00
004016FA     00             DB 00
004016FB     00             DB 00
004016FC     00             DB 00
004016FD     00             DB 00
004016FE     00             DB 00
004016FF     00             DB 00
00401700     00             DB 00
00401701     00             DB 00
00401702     00             DB 00
00401703     00             DB 00
00401704     00             DB 00
00401705     00             DB 00
00401706     00             DB 00
00401707     00             DB 00
00401708     00             DB 00
00401709     00             DB 00
0040170A     00             DB 00
0040170B     00             DB 00
0040170C     00             DB 00
0040170D     00             DB 00
0040170E     00             DB 00
0040170F     00             DB 00
00401710     00             DB 00
00401711     00             DB 00
00401712     00             DB 00
00401713     00             DB 00
00401714     00             DB 00
00401715     00             DB 00
00401716     00             DB 00
00401717     00             DB 00
00401718     00             DB 00
00401719     00             DB 00
0040171A     00             DB 00
0040171B     00             DB 00
0040171C     00             DB 00
0040171D     00             DB 00
0040171E     00             DB 00
0040171F     00             DB 00
00401720     00             DB 00
00401721     00             DB 00
00401722     00             DB 00
00401723     00             DB 00
00401724     00             DB 00
00401725     00             DB 00
00401726     00             DB 00
00401727     00             DB 00
00401728     00             DB 00
00401729     00             DB 00
0040172A     00             DB 00
0040172B     00             DB 00
0040172C     00             DB 00
0040172D     00             DB 00
0040172E     00             DB 00
0040172F     00             DB 00
00401730     00             DB 00
00401731     00             DB 00
00401732     00             DB 00
00401733     00             DB 00
00401734     00             DB 00
00401735     00             DB 00
00401736     00             DB 00
00401737     00             DB 00
00401738     00             DB 00
00401739     00             DB 00
0040173A     00             DB 00
0040173B     00             DB 00
0040173C     00             DB 00
0040173D     00             DB 00
0040173E     00             DB 00
0040173F     00             DB 00
00401740     00             DB 00
00401741     00             DB 00
00401742     00             DB 00
00401743     00             DB 00
00401744     00             DB 00
00401745     00             DB 00
00401746     00             DB 00
00401747     00             DB 00
00401748     00             DB 00
00401749     00             DB 00
0040174A     00             DB 00
0040174B     00             DB 00
0040174C     00             DB 00
0040174D     00             DB 00
0040174E     00             DB 00
0040174F     00             DB 00
00401750     00             DB 00
00401751     00             DB 00
00401752     00             DB 00
00401753     00             DB 00
00401754     00             DB 00
00401755     00             DB 00
00401756     00             DB 00
00401757     00             DB 00
00401758     00             DB 00
00401759     00             DB 00
0040175A     00             DB 00
0040175B     00             DB 00
0040175C     00             DB 00
0040175D     00             DB 00
0040175E     00             DB 00
0040175F     00             DB 00
00401760     00             DB 00
00401761     00             DB 00
00401762     00             DB 00
00401763     00             DB 00
00401764     00             DB 00
00401765     00             DB 00
00401766     00             DB 00
00401767     00             DB 00
00401768     00             DB 00
00401769     00             DB 00
0040176A     00             DB 00
0040176B     00             DB 00
0040176C     00             DB 00
0040176D     00             DB 00
0040176E     00             DB 00
0040176F     00             DB 00
00401770     00             DB 00
00401771     00             DB 00
00401772     00             DB 00
00401773     00             DB 00
00401774     00             DB 00
00401775     00             DB 00
00401776     00             DB 00
00401777     00             DB 00
00401778     00             DB 00
00401779     00             DB 00
0040177A     00             DB 00
0040177B     00             DB 00
0040177C     00             DB 00
0040177D     00             DB 00
0040177E     00             DB 00
0040177F     00             DB 00
00401780     00             DB 00
00401781     00             DB 00
00401782     00             DB 00
00401783     00             DB 00
00401784     00             DB 00
00401785     00             DB 00
00401786     00             DB 00
00401787     00             DB 00
00401788     00             DB 00
00401789     00             DB 00
0040178A     00             DB 00
0040178B     00             DB 00
0040178C     00             DB 00
0040178D     00             DB 00
0040178E     00             DB 00
0040178F     00             DB 00
00401790     00             DB 00
00401791     00             DB 00
00401792     00             DB 00
00401793     00             DB 00
00401794     00             DB 00
00401795     00             DB 00
00401796     00             DB 00
00401797     00             DB 00
00401798     00             DB 00
00401799     00             DB 00
0040179A     00             DB 00
0040179B     00             DB 00
0040179C     00             DB 00
0040179D     00             DB 00
0040179E     00             DB 00
0040179F     00             DB 00
004017A0     00             DB 00
004017A1     00             DB 00
004017A2     00             DB 00
004017A3     00             DB 00
004017A4     00             DB 00
004017A5     00             DB 00
004017A6     00             DB 00
004017A7     00             DB 00
004017A8     00             DB 00
004017A9     00             DB 00
004017AA     00             DB 00
004017AB     00             DB 00
004017AC     00             DB 00
004017AD     00             DB 00
004017AE     00             DB 00
004017AF     00             DB 00
004017B0     00             DB 00
004017B1     00             DB 00
004017B2     00             DB 00
004017B3     00             DB 00
004017B4     00             DB 00
004017B5     00             DB 00
004017B6     00             DB 00
004017B7     00             DB 00
004017B8     00             DB 00
004017B9     00             DB 00
004017BA     00             DB 00
004017BB     00             DB 00
004017BC     00             DB 00
004017BD     00             DB 00
004017BE     00             DB 00
004017BF     00             DB 00
004017C0     00             DB 00
004017C1     00             DB 00
004017C2     00             DB 00
004017C3     00             DB 00
004017C4     00             DB 00
004017C5     00             DB 00
004017C6     00             DB 00
004017C7     00             DB 00
004017C8     00             DB 00
004017C9     00             DB 00
004017CA     00             DB 00
004017CB     00             DB 00
004017CC     00             DB 00
004017CD     00             DB 00
004017CE     00             DB 00
004017CF     00             DB 00
004017D0     00             DB 00
004017D1     00             DB 00
004017D2     00             DB 00
004017D3     00             DB 00
004017D4     00             DB 00
004017D5     00             DB 00
004017D6     00             DB 00
004017D7     00             DB 00
004017D8     00             DB 00
004017D9     00             DB 00
004017DA     00             DB 00
004017DB     00             DB 00
004017DC     00             DB 00
004017DD     00             DB 00
004017DE     00             DB 00
004017DF     00             DB 00
004017E0     00             DB 00
004017E1     00             DB 00
004017E2     00             DB 00
004017E3     00             DB 00
004017E4     00             DB 00
004017E5     00             DB 00
004017E6     00             DB 00
004017E7     00             DB 00
004017E8     00             DB 00
004017E9     00             DB 00
004017EA     00             DB 00
004017EB     00             DB 00
004017EC     00             DB 00
004017ED     00             DB 00
004017EE     00             DB 00
004017EF     00             DB 00
004017F0     00             DB 00
004017F1     00             DB 00
004017F2     00             DB 00
004017F3     00             DB 00
004017F4     00             DB 00
004017F5     00             DB 00
004017F6     00             DB 00
004017F7     00             DB 00
004017F8     00             DB 00
004017F9     00             DB 00
004017FA     00             DB 00
004017FB     00             DB 00
004017FC     00             DB 00
004017FD     00             DB 00
004017FE     00             DB 00
004017FF     00             DB 00
00401800     00             DB 00
00401801     00             DB 00
00401802     00             DB 00
00401803     00             DB 00
00401804     00             DB 00
00401805     00             DB 00
00401806     00             DB 00
00401807     00             DB 00
00401808     00             DB 00
00401809     00             DB 00
0040180A     00             DB 00
0040180B     00             DB 00
0040180C     00             DB 00
0040180D     00             DB 00
0040180E     00             DB 00
0040180F     00             DB 00
00401810     00             DB 00
00401811     00             DB 00
00401812     00             DB 00
00401813     00             DB 00
00401814     00             DB 00
00401815     00             DB 00
00401816     00             DB 00
00401817     00             DB 00
00401818     00             DB 00
00401819     00             DB 00
0040181A     00             DB 00
0040181B     00             DB 00
0040181C     00             DB 00
0040181D     00             DB 00
0040181E     00             DB 00
0040181F     00             DB 00
00401820     00             DB 00
00401821     00             DB 00
00401822     00             DB 00
00401823     00             DB 00
00401824     00             DB 00
00401825     00             DB 00
00401826     00             DB 00
00401827     00             DB 00
00401828     00             DB 00
00401829     00             DB 00
0040182A     00             DB 00
0040182B     00             DB 00
0040182C     00             DB 00
0040182D     00             DB 00
0040182E     00             DB 00
0040182F     00             DB 00
00401830     00             DB 00
00401831     00             DB 00
00401832     00             DB 00
00401833     00             DB 00
00401834     00             DB 00
00401835     00             DB 00
00401836     00             DB 00
00401837     00             DB 00
00401838     00             DB 00
00401839     00             DB 00
0040183A     00             DB 00
0040183B     00             DB 00
0040183C     00             DB 00
0040183D     00             DB 00
0040183E     00             DB 00
0040183F     00             DB 00
00401840     00             DB 00
00401841     00             DB 00
00401842     00             DB 00
00401843     00             DB 00
00401844     00             DB 00
00401845     00             DB 00
00401846     00             DB 00
00401847     00             DB 00
00401848     00             DB 00
00401849     00             DB 00
0040184A     00             DB 00
0040184B     00             DB 00
0040184C     00             DB 00
0040184D     00             DB 00
0040184E     00             DB 00
0040184F     00             DB 00
00401850     00             DB 00
00401851     00             DB 00
00401852     00             DB 00
00401853     00             DB 00
00401854     00             DB 00
00401855     00             DB 00
00401856     00             DB 00
00401857     00             DB 00
00401858     00             DB 00
00401859     00             DB 00
0040185A     00             DB 00
0040185B     00             DB 00
0040185C     00             DB 00
0040185D     00             DB 00
0040185E     00             DB 00
0040185F     00             DB 00
00401860     00             DB 00
00401861     00             DB 00
00401862     00             DB 00
00401863     00             DB 00
00401864     00             DB 00
00401865     00             DB 00
00401866     00             DB 00
00401867     00             DB 00
00401868     00             DB 00
00401869     00             DB 00
0040186A     00             DB 00
0040186B     00             DB 00
0040186C     00             DB 00
0040186D     00             DB 00
0040186E     00             DB 00
0040186F     00             DB 00
00401870     00             DB 00
00401871     00             DB 00
00401872     00             DB 00
00401873     00             DB 00
00401874     00             DB 00
00401875     00             DB 00
00401876     00             DB 00
00401877     00             DB 00
00401878     00             DB 00
00401879     00             DB 00
0040187A     00             DB 00
0040187B     00             DB 00
0040187C     00             DB 00
0040187D     00             DB 00
0040187E     00             DB 00
0040187F     00             DB 00
00401880     00             DB 00
00401881     00             DB 00
00401882     00             DB 00
00401883     00             DB 00
00401884     00             DB 00
00401885     00             DB 00
00401886     00             DB 00
00401887     00             DB 00
00401888     00             DB 00
00401889     00             DB 00
0040188A     00             DB 00
0040188B     00             DB 00
0040188C     00             DB 00
0040188D     00             DB 00
0040188E     00             DB 00
0040188F     00             DB 00
00401890     00             DB 00
00401891     00             DB 00
00401892     00             DB 00
00401893     00             DB 00
00401894     00             DB 00
00401895     00             DB 00
00401896     00             DB 00
00401897     00             DB 00
00401898     00             DB 00
00401899     00             DB 00
0040189A     00             DB 00
0040189B     00             DB 00
0040189C     00             DB 00
0040189D     00             DB 00
0040189E     00             DB 00
0040189F     00             DB 00
004018A0     00             DB 00
004018A1     00             DB 00
004018A2     00             DB 00
004018A3     00             DB 00
004018A4     00             DB 00
004018A5     00             DB 00
004018A6     00             DB 00
004018A7     00             DB 00
004018A8     00             DB 00
004018A9     00             DB 00
004018AA     00             DB 00
004018AB     00             DB 00
004018AC     00             DB 00
004018AD     00             DB 00
004018AE     00             DB 00
004018AF     00             DB 00
004018B0     00             DB 00
004018B1     00             DB 00
004018B2     00             DB 00
004018B3     00             DB 00
004018B4     00             DB 00
004018B5     00             DB 00
004018B6     00             DB 00
004018B7     00             DB 00
004018B8     00             DB 00
004018B9     00             DB 00
004018BA     00             DB 00
004018BB     00             DB 00
004018BC     00             DB 00
004018BD     00             DB 00
004018BE     00             DB 00
004018BF     00             DB 00
004018C0     00             DB 00
004018C1     00             DB 00
004018C2     00             DB 00
004018C3     00             DB 00
004018C4     00             DB 00
004018C5     00             DB 00
004018C6     00             DB 00
004018C7     00             DB 00
004018C8     00             DB 00
004018C9     00             DB 00
004018CA     00             DB 00
004018CB     00             DB 00
004018CC     00             DB 00
004018CD     00             DB 00
004018CE     00             DB 00
004018CF     00             DB 00
004018D0     00             DB 00
004018D1     00             DB 00
004018D2     00             DB 00
004018D3     00             DB 00
004018D4     00             DB 00
004018D5     00             DB 00
004018D6     00             DB 00
004018D7     00             DB 00
004018D8     00             DB 00
004018D9     00             DB 00
004018DA     00             DB 00
004018DB     00             DB 00
004018DC     00             DB 00
004018DD     00             DB 00
004018DE     00             DB 00
004018DF     00             DB 00
004018E0     00             DB 00
004018E1     00             DB 00
004018E2     00             DB 00
004018E3     00             DB 00
004018E4     00             DB 00
004018E5     00             DB 00
004018E6     00             DB 00
004018E7     00             DB 00
004018E8     00             DB 00
004018E9     00             DB 00
004018EA     00             DB 00
004018EB     00             DB 00
004018EC     00             DB 00
004018ED     00             DB 00
004018EE     00             DB 00
004018EF     00             DB 00
004018F0     00             DB 00
004018F1     00             DB 00
004018F2     00             DB 00
004018F3     00             DB 00
004018F4     00             DB 00
004018F5     00             DB 00
004018F6     00             DB 00
004018F7     00             DB 00
004018F8     00             DB 00
004018F9     00             DB 00
004018FA     00             DB 00
004018FB     00             DB 00
004018FC     00             DB 00
004018FD     00             DB 00
004018FE     00             DB 00
004018FF     00             DB 00
00401900     00             DB 00
00401901     00             DB 00
00401902     00             DB 00
00401903     00             DB 00
00401904     00             DB 00
00401905     00             DB 00
00401906     00             DB 00
00401907     00             DB 00
00401908     00             DB 00
00401909     00             DB 00
0040190A     00             DB 00
0040190B     00             DB 00
0040190C     00             DB 00
0040190D     00             DB 00
0040190E     00             DB 00
0040190F     00             DB 00
00401910     00             DB 00
00401911     00             DB 00
00401912     00             DB 00
00401913     00             DB 00
00401914     00             DB 00
00401915     00             DB 00
00401916     00             DB 00
00401917     00             DB 00
00401918     00             DB 00
00401919     00             DB 00
0040191A     00             DB 00
0040191B     00             DB 00
0040191C     00             DB 00
0040191D     00             DB 00
0040191E     00             DB 00
0040191F     00             DB 00
00401920     00             DB 00
00401921     00             DB 00
00401922     00             DB 00
00401923     00             DB 00
00401924     00             DB 00
00401925     00             DB 00
00401926     00             DB 00
00401927     00             DB 00
00401928     00             DB 00
00401929     00             DB 00
0040192A     00             DB 00
0040192B     00             DB 00
0040192C     00             DB 00
0040192D     00             DB 00
0040192E     00             DB 00
0040192F     00             DB 00
00401930     00             DB 00
00401931     00             DB 00
00401932     00             DB 00
00401933     00             DB 00
00401934     00             DB 00
00401935     00             DB 00
00401936     00             DB 00
00401937     00             DB 00
00401938     00             DB 00
00401939     00             DB 00
0040193A     00             DB 00
0040193B     00             DB 00
0040193C     00             DB 00
0040193D     00             DB 00
0040193E     00             DB 00
0040193F     00             DB 00
00401940     00             DB 00
00401941     00             DB 00
00401942     00             DB 00
00401943     00             DB 00
00401944     00             DB 00
00401945     00             DB 00
00401946     00             DB 00
00401947     00             DB 00
00401948     00             DB 00
00401949     00             DB 00
0040194A     00             DB 00
0040194B     00             DB 00
0040194C     00             DB 00
0040194D     00             DB 00
0040194E     00             DB 00
0040194F     00             DB 00
00401950     00             DB 00
00401951     00             DB 00
00401952     00             DB 00
00401953     00             DB 00
00401954     00             DB 00
00401955     00             DB 00
00401956     00             DB 00
00401957     00             DB 00
00401958     00             DB 00
00401959     00             DB 00
0040195A     00             DB 00
0040195B     00             DB 00
0040195C     00             DB 00
0040195D     00             DB 00
0040195E     00             DB 00
0040195F     00             DB 00
00401960     00             DB 00
00401961     00             DB 00
00401962     00             DB 00
00401963     00             DB 00
00401964     00             DB 00
00401965     00             DB 00
00401966     00             DB 00
00401967     00             DB 00
00401968     00             DB 00
00401969     00             DB 00
0040196A     00             DB 00
0040196B     00             DB 00
0040196C     00             DB 00
0040196D     00             DB 00
0040196E     00             DB 00
0040196F     00             DB 00
00401970     00             DB 00
00401971     00             DB 00
00401972     00             DB 00
00401973     00             DB 00
00401974     00             DB 00
00401975     00             DB 00
00401976     00             DB 00
00401977     00             DB 00
00401978     00             DB 00
00401979     00             DB 00
0040197A     00             DB 00
0040197B     00             DB 00
0040197C     00             DB 00
0040197D     00             DB 00
0040197E     00             DB 00
0040197F     00             DB 00
00401980     00             DB 00
00401981     00             DB 00
00401982     00             DB 00
00401983     00             DB 00
00401984     00             DB 00
00401985     00             DB 00
00401986     00             DB 00
00401987     00             DB 00
00401988     00             DB 00
00401989     00             DB 00
0040198A     00             DB 00
0040198B     00             DB 00
0040198C     00             DB 00
0040198D     00             DB 00
0040198E     00             DB 00
0040198F     00             DB 00
00401990     00             DB 00
00401991     00             DB 00
00401992     00             DB 00
00401993     00             DB 00
00401994     00             DB 00
00401995     00             DB 00
00401996     00             DB 00
00401997     00             DB 00
00401998     00             DB 00
00401999     00             DB 00
0040199A     00             DB 00
0040199B     00             DB 00
0040199C     00             DB 00
0040199D     00             DB 00
0040199E     00             DB 00
0040199F     00             DB 00
004019A0     00             DB 00
004019A1     00             DB 00
004019A2     00             DB 00
004019A3     00             DB 00
004019A4     00             DB 00
004019A5     00             DB 00
004019A6     00             DB 00
004019A7     00             DB 00
004019A8     00             DB 00
004019A9     00             DB 00
004019AA     00             DB 00
004019AB     00             DB 00
004019AC     00             DB 00
004019AD     00             DB 00
004019AE     00             DB 00
004019AF     00             DB 00
004019B0     00             DB 00
004019B1     00             DB 00
004019B2     00             DB 00
004019B3     00             DB 00
004019B4     00             DB 00
004019B5     00             DB 00
004019B6     00             DB 00
004019B7     00             DB 00
004019B8     00             DB 00
004019B9     00             DB 00
004019BA     00             DB 00
004019BB     00             DB 00
004019BC     00             DB 00
004019BD     00             DB 00
004019BE     00             DB 00
004019BF     00             DB 00
004019C0     00             DB 00
004019C1     00             DB 00
004019C2     00             DB 00
004019C3     00             DB 00
004019C4     00             DB 00
004019C5     00             DB 00
004019C6     00             DB 00
004019C7     00             DB 00
004019C8     00             DB 00
004019C9     00             DB 00
004019CA     00             DB 00
004019CB     00             DB 00
004019CC     00             DB 00
004019CD     00             DB 00
004019CE     00             DB 00
004019CF     00             DB 00
004019D0     00             DB 00
004019D1     00             DB 00
004019D2     00             DB 00
004019D3     00             DB 00
004019D4     00             DB 00
004019D5     00             DB 00
004019D6     00             DB 00
004019D7     00             DB 00
004019D8     00             DB 00
004019D9     00             DB 00
004019DA     00             DB 00
004019DB     00             DB 00
004019DC     00             DB 00
004019DD     00             DB 00
004019DE     00             DB 00
004019DF     00             DB 00
004019E0     00             DB 00
004019E1     00             DB 00
004019E2     00             DB 00
004019E3     00             DB 00
004019E4     00             DB 00
004019E5     00             DB 00
004019E6     00             DB 00
004019E7     00             DB 00
004019E8     00             DB 00
004019E9     00             DB 00
004019EA     00             DB 00
004019EB     00             DB 00
004019EC     00             DB 00
004019ED     00             DB 00
004019EE     00             DB 00
004019EF     00             DB 00
004019F0     00             DB 00
004019F1     00             DB 00
004019F2     00             DB 00
004019F3     00             DB 00
004019F4     00             DB 00
004019F5     00             DB 00
004019F6     00             DB 00
004019F7     00             DB 00
004019F8     00             DB 00
004019F9     00             DB 00
004019FA     00             DB 00
004019FB     00             DB 00
004019FC     00             DB 00
004019FD     00             DB 00
004019FE     00             DB 00
004019FF     00             DB 00
00401A00     00             DB 00
00401A01     00             DB 00
00401A02     00             DB 00
00401A03     00             DB 00
00401A04     00             DB 00
00401A05     00             DB 00
00401A06     00             DB 00
00401A07     00             DB 00
00401A08     00             DB 00
00401A09     00             DB 00
00401A0A     00             DB 00
00401A0B     00             DB 00
00401A0C     00             DB 00
00401A0D     00             DB 00
00401A0E     00             DB 00
00401A0F     00             DB 00
00401A10     00             DB 00
00401A11     00             DB 00
00401A12     00             DB 00
00401A13     00             DB 00
00401A14     00             DB 00
00401A15     00             DB 00
00401A16     00             DB 00
00401A17     00             DB 00
00401A18     00             DB 00
00401A19     00             DB 00
00401A1A     00             DB 00
00401A1B     00             DB 00
00401A1C     00             DB 00
00401A1D     00             DB 00
00401A1E     00             DB 00
00401A1F     00             DB 00
00401A20     00             DB 00
00401A21     00             DB 00
00401A22     00             DB 00
00401A23     00             DB 00
00401A24     00             DB 00
00401A25     00             DB 00
00401A26     00             DB 00
00401A27     00             DB 00
00401A28     00             DB 00
00401A29     00             DB 00
00401A2A     00             DB 00
00401A2B     00             DB 00
00401A2C     00             DB 00
00401A2D     00             DB 00
00401A2E     00             DB 00
00401A2F     00             DB 00
00401A30     00             DB 00
00401A31     00             DB 00
00401A32     00             DB 00
00401A33     00             DB 00
00401A34     00             DB 00
00401A35     00             DB 00
00401A36     00             DB 00
00401A37     00             DB 00
00401A38     00             DB 00
00401A39     00             DB 00
00401A3A     00             DB 00
00401A3B     00             DB 00
00401A3C     00             DB 00
00401A3D     00             DB 00
00401A3E     00             DB 00
00401A3F     00             DB 00
00401A40     00             DB 00
00401A41     00             DB 00
00401A42     00             DB 00
00401A43     00             DB 00
00401A44     00             DB 00
00401A45     00             DB 00
00401A46     00             DB 00
00401A47     00             DB 00
00401A48     00             DB 00
00401A49     00             DB 00
00401A4A     00             DB 00
00401A4B     00             DB 00
00401A4C     00             DB 00
00401A4D     00             DB 00
00401A4E     00             DB 00
00401A4F     00             DB 00
00401A50     00             DB 00
00401A51     00             DB 00
00401A52     00             DB 00
00401A53     00             DB 00
00401A54     00             DB 00
00401A55     00             DB 00
00401A56     00             DB 00
00401A57     00             DB 00
00401A58     00             DB 00
00401A59     00             DB 00
00401A5A     00             DB 00
00401A5B     00             DB 00
00401A5C     00             DB 00
00401A5D     00             DB 00
00401A5E     00             DB 00
00401A5F     00             DB 00
00401A60     00             DB 00
00401A61     00             DB 00
00401A62     00             DB 00
00401A63     00             DB 00
00401A64     00             DB 00
00401A65     00             DB 00
00401A66     00             DB 00
00401A67     00             DB 00
00401A68     00             DB 00
00401A69     00             DB 00
00401A6A     00             DB 00
00401A6B     00             DB 00
00401A6C     00             DB 00
00401A6D     00             DB 00
00401A6E     00             DB 00
00401A6F     00             DB 00
00401A70     00             DB 00
00401A71     00             DB 00
00401A72     00             DB 00
00401A73     00             DB 00
00401A74     00             DB 00
00401A75     00             DB 00
00401A76     00             DB 00
00401A77     00             DB 00
00401A78     00             DB 00
00401A79     00             DB 00
00401A7A     00             DB 00
00401A7B     00             DB 00
00401A7C     00             DB 00
00401A7D     00             DB 00
00401A7E     00             DB 00
00401A7F     00             DB 00
00401A80     00             DB 00
00401A81     00             DB 00
00401A82     00             DB 00
00401A83     00             DB 00
00401A84     00             DB 00
00401A85     00             DB 00
00401A86     00             DB 00
00401A87     00             DB 00
00401A88     00             DB 00
00401A89     00             DB 00
00401A8A     00             DB 00
00401A8B     00             DB 00
00401A8C     00             DB 00
00401A8D     00             DB 00
00401A8E     00             DB 00
00401A8F     00             DB 00
00401A90     00             DB 00
00401A91     00             DB 00
00401A92     00             DB 00
00401A93     00             DB 00
00401A94     00             DB 00
00401A95     00             DB 00
00401A96     00             DB 00
00401A97     00             DB 00
00401A98     00             DB 00
00401A99     00             DB 00
00401A9A     00             DB 00
00401A9B     00             DB 00
00401A9C     00             DB 00
00401A9D     00             DB 00
00401A9E     00             DB 00
00401A9F     00             DB 00
00401AA0     00             DB 00
00401AA1     00             DB 00
00401AA2     00             DB 00
00401AA3     00             DB 00
00401AA4     00             DB 00
00401AA5     00             DB 00
00401AA6     00             DB 00
00401AA7     00             DB 00
00401AA8     00             DB 00
00401AA9     00             DB 00
00401AAA     00             DB 00
00401AAB     00             DB 00
00401AAC     00             DB 00
00401AAD     00             DB 00
00401AAE     00             DB 00
00401AAF     00             DB 00
00401AB0     00             DB 00
00401AB1     00             DB 00
00401AB2     00             DB 00
00401AB3     00             DB 00
00401AB4     00             DB 00
00401AB5     00             DB 00
00401AB6     00             DB 00
00401AB7     00             DB 00
00401AB8     00             DB 00
00401AB9     00             DB 00
00401ABA     00             DB 00
00401ABB     00             DB 00
00401ABC     00             DB 00
00401ABD     00             DB 00
00401ABE     00             DB 00
00401ABF     00             DB 00
00401AC0     00             DB 00
00401AC1     00             DB 00
00401AC2     00             DB 00
00401AC3     00             DB 00
00401AC4     00             DB 00
00401AC5     00             DB 00
00401AC6     00             DB 00
00401AC7     00             DB 00
00401AC8     00             DB 00
00401AC9     00             DB 00
00401ACA     00             DB 00
00401ACB     00             DB 00
00401ACC     00             DB 00
00401ACD     00             DB 00
00401ACE     00             DB 00
00401ACF     00             DB 00
00401AD0     00             DB 00
00401AD1     00             DB 00
00401AD2     00             DB 00
00401AD3     00             DB 00
00401AD4     00             DB 00
00401AD5     00             DB 00
00401AD6     00             DB 00
00401AD7     00             DB 00
00401AD8     00             DB 00
00401AD9     00             DB 00
00401ADA     00             DB 00
00401ADB     00             DB 00
00401ADC     00             DB 00
00401ADD     00             DB 00
00401ADE     00             DB 00
00401ADF     00             DB 00
00401AE0     00             DB 00
00401AE1     00             DB 00
00401AE2     00             DB 00
00401AE3     00             DB 00
00401AE4     00             DB 00
00401AE5     00             DB 00
00401AE6     00             DB 00
00401AE7     00             DB 00
00401AE8     00             DB 00
00401AE9     00             DB 00
00401AEA     00             DB 00
00401AEB     00             DB 00
00401AEC     00             DB 00
00401AED     00             DB 00
00401AEE     00             DB 00
00401AEF     00             DB 00
00401AF0     00             DB 00
00401AF1     00             DB 00
00401AF2     00             DB 00
00401AF3     00             DB 00
00401AF4     00             DB 00
00401AF5     00             DB 00
00401AF6     00             DB 00
00401AF7     00             DB 00
00401AF8     00             DB 00
00401AF9     00             DB 00
00401AFA     00             DB 00
00401AFB     00             DB 00
00401AFC     00             DB 00
00401AFD     00             DB 00
00401AFE     00             DB 00
00401AFF     00             DB 00
00401B00     00             DB 00
00401B01     00             DB 00
00401B02     00             DB 00
00401B03     00             DB 00
00401B04     00             DB 00
00401B05     00             DB 00
00401B06     00             DB 00
00401B07     00             DB 00
00401B08     00             DB 00
00401B09     00             DB 00
00401B0A     00             DB 00
00401B0B     00             DB 00
00401B0C     00             DB 00
00401B0D     00             DB 00
00401B0E     00             DB 00
00401B0F     00             DB 00
00401B10     00             DB 00
00401B11     00             DB 00
00401B12     00             DB 00
00401B13     00             DB 00
00401B14     00             DB 00
00401B15     00             DB 00
00401B16     00             DB 00
00401B17     00             DB 00
00401B18     00             DB 00
00401B19     00             DB 00
00401B1A     00             DB 00
00401B1B     00             DB 00
00401B1C     00             DB 00
00401B1D     00             DB 00
00401B1E     00             DB 00
00401B1F     00             DB 00
00401B20     00             DB 00
00401B21     00             DB 00
00401B22     00             DB 00
00401B23     00             DB 00
00401B24     00             DB 00
00401B25     00             DB 00
00401B26     00             DB 00
00401B27     00             DB 00
00401B28     00             DB 00
00401B29     00             DB 00
00401B2A     00             DB 00
00401B2B     00             DB 00
00401B2C     00             DB 00
00401B2D     00             DB 00
00401B2E     00             DB 00
00401B2F     00             DB 00
00401B30     00             DB 00
00401B31     00             DB 00
00401B32     00             DB 00
00401B33     00             DB 00
00401B34     00             DB 00
00401B35     00             DB 00
00401B36     00             DB 00
00401B37     00             DB 00
00401B38     00             DB 00
00401B39     00             DB 00
00401B3A     00             DB 00
00401B3B     00             DB 00
00401B3C     00             DB 00
00401B3D     00             DB 00
00401B3E     00             DB 00
00401B3F     00             DB 00
00401B40     00             DB 00
00401B41     00             DB 00
00401B42     00             DB 00
00401B43     00             DB 00
00401B44     00             DB 00
00401B45     00             DB 00
00401B46     00             DB 00
00401B47     00             DB 00
00401B48     00             DB 00
00401B49     00             DB 00
00401B4A     00             DB 00
00401B4B     00             DB 00
00401B4C     00             DB 00
00401B4D     00             DB 00
00401B4E     00             DB 00
00401B4F     00             DB 00
00401B50     00             DB 00
00401B51     00             DB 00
00401B52     00             DB 00
00401B53     00             DB 00
00401B54     00             DB 00
00401B55     00             DB 00
00401B56     00             DB 00
00401B57     00             DB 00
00401B58     00             DB 00
00401B59     00             DB 00
00401B5A     00             DB 00
00401B5B     00             DB 00
00401B5C     00             DB 00
00401B5D     00             DB 00
00401B5E     00             DB 00
00401B5F     00             DB 00
00401B60     00             DB 00
00401B61     00             DB 00
00401B62     00             DB 00
00401B63     00             DB 00
00401B64     00             DB 00
00401B65     00             DB 00
00401B66     00             DB 00
00401B67     00             DB 00
00401B68     00             DB 00
00401B69     00             DB 00
00401B6A     00             DB 00
00401B6B     00             DB 00
00401B6C     00             DB 00
00401B6D     00             DB 00
00401B6E     00             DB 00
00401B6F     00             DB 00
00401B70     00             DB 00
00401B71     00             DB 00
00401B72     00             DB 00
00401B73     00             DB 00
00401B74     00             DB 00
00401B75     00             DB 00
00401B76     00             DB 00
00401B77     00             DB 00
00401B78     00             DB 00
00401B79     00             DB 00
00401B7A     00             DB 00
00401B7B     00             DB 00
00401B7C     00             DB 00
00401B7D     00             DB 00
00401B7E     00             DB 00
00401B7F     00             DB 00
00401B80     00             DB 00
00401B81     00             DB 00
00401B82     00             DB 00
00401B83     00             DB 00
00401B84     00             DB 00
00401B85     00             DB 00
00401B86     00             DB 00
00401B87     00             DB 00
00401B88     00             DB 00
00401B89     00             DB 00
00401B8A     00             DB 00
00401B8B     00             DB 00
00401B8C     00             DB 00
00401B8D     00             DB 00
00401B8E     00             DB 00
00401B8F     00             DB 00
00401B90     00             DB 00
00401B91     00             DB 00
00401B92     00             DB 00
00401B93     00             DB 00
00401B94     00             DB 00
00401B95     00             DB 00
00401B96     00             DB 00
00401B97     00             DB 00
00401B98     00             DB 00
00401B99     00             DB 00
00401B9A     00             DB 00
00401B9B     00             DB 00
00401B9C     00             DB 00
00401B9D     00             DB 00
00401B9E     00             DB 00
00401B9F     00             DB 00
00401BA0     00             DB 00
00401BA1     00             DB 00
00401BA2     00             DB 00
00401BA3     00             DB 00
00401BA4     00             DB 00
00401BA5     00             DB 00
00401BA6     00             DB 00
00401BA7     00             DB 00
00401BA8     00             DB 00
00401BA9     00             DB 00
00401BAA     00             DB 00
00401BAB     00             DB 00
00401BAC     00             DB 00
00401BAD     00             DB 00
00401BAE     00             DB 00
00401BAF     00             DB 00
00401BB0     00             DB 00
00401BB1     00             DB 00
00401BB2     00             DB 00
00401BB3     00             DB 00
00401BB4     00             DB 00
00401BB5     00             DB 00
00401BB6     00             DB 00
00401BB7     00             DB 00
00401BB8     00             DB 00
00401BB9     00             DB 00
00401BBA     00             DB 00
00401BBB     00             DB 00
00401BBC     00             DB 00
00401BBD     00             DB 00
00401BBE     00             DB 00
00401BBF     00             DB 00
00401BC0     00             DB 00
00401BC1     00             DB 00
00401BC2     00             DB 00
00401BC3     00             DB 00
00401BC4     00             DB 00
00401BC5     00             DB 00
00401BC6     00             DB 00
00401BC7     00             DB 00
00401BC8     00             DB 00
00401BC9     00             DB 00
00401BCA     00             DB 00
00401BCB     00             DB 00
00401BCC     00             DB 00
00401BCD     00             DB 00
00401BCE     00             DB 00
00401BCF     00             DB 00
00401BD0     00             DB 00
00401BD1     00             DB 00
00401BD2     00             DB 00
00401BD3     00             DB 00
00401BD4     00             DB 00
00401BD5     00             DB 00
00401BD6     00             DB 00
00401BD7     00             DB 00
00401BD8     00             DB 00
00401BD9     00             DB 00
00401BDA     00             DB 00
00401BDB     00             DB 00
00401BDC     00             DB 00
00401BDD     00             DB 00
00401BDE     00             DB 00
00401BDF     00             DB 00
00401BE0     00             DB 00
00401BE1     00             DB 00
00401BE2     00             DB 00
00401BE3     00             DB 00
00401BE4     00             DB 00
00401BE5     00             DB 00
00401BE6     00             DB 00
00401BE7     00             DB 00
00401BE8     00             DB 00
00401BE9     00             DB 00
00401BEA     00             DB 00
00401BEB     00             DB 00
00401BEC     00             DB 00
00401BED     00             DB 00
00401BEE     00             DB 00
00401BEF     00             DB 00
00401BF0     00             DB 00
00401BF1     00             DB 00
00401BF2     00             DB 00
00401BF3     00             DB 00
00401BF4     00             DB 00
00401BF5     00             DB 00
00401BF6     00             DB 00
00401BF7     00             DB 00
00401BF8     00             DB 00
00401BF9     00             DB 00
00401BFA     00             DB 00
00401BFB     00             DB 00
00401BFC     00             DB 00
00401BFD     00             DB 00
00401BFE     00             DB 00
00401BFF     00             DB 00
00401C00     00             DB 00
00401C01     00             DB 00
00401C02     00             DB 00
00401C03     00             DB 00
00401C04     00             DB 00
00401C05     00             DB 00
00401C06     00             DB 00
00401C07     00             DB 00
00401C08     00             DB 00
00401C09     00             DB 00
00401C0A     00             DB 00
00401C0B     00             DB 00
00401C0C     00             DB 00
00401C0D     00             DB 00
00401C0E     00             DB 00
00401C0F     00             DB 00
00401C10     00             DB 00
00401C11     00             DB 00
00401C12     00             DB 00
00401C13     00             DB 00
00401C14     00             DB 00
00401C15     00             DB 00
00401C16     00             DB 00
00401C17     00             DB 00
00401C18     00             DB 00
00401C19     00             DB 00
00401C1A     00             DB 00
00401C1B     00             DB 00
00401C1C     00             DB 00
00401C1D     00             DB 00
00401C1E     00             DB 00
00401C1F     00             DB 00
00401C20     00             DB 00
00401C21     00             DB 00
00401C22     00             DB 00
00401C23     00             DB 00
00401C24     00             DB 00
00401C25     00             DB 00
00401C26     00             DB 00
00401C27     00             DB 00
00401C28     00             DB 00
00401C29     00             DB 00
00401C2A     00             DB 00
00401C2B     00             DB 00
00401C2C     00             DB 00
00401C2D     00             DB 00
00401C2E     00             DB 00
00401C2F     00             DB 00
00401C30     00             DB 00
00401C31     00             DB 00
00401C32     00             DB 00
00401C33     00             DB 00
00401C34     00             DB 00
00401C35     00             DB 00
00401C36     00             DB 00
00401C37     00             DB 00
00401C38     00             DB 00
00401C39     00             DB 00
00401C3A     00             DB 00
00401C3B     00             DB 00
00401C3C     00             DB 00
00401C3D     00             DB 00
00401C3E     00             DB 00
00401C3F     00             DB 00
00401C40     00             DB 00
00401C41     00             DB 00
00401C42     00             DB 00
00401C43     00             DB 00
00401C44     00             DB 00
00401C45     00             DB 00
00401C46     00             DB 00
00401C47     00             DB 00
00401C48     00             DB 00
00401C49     00             DB 00
00401C4A     00             DB 00
00401C4B     00             DB 00
00401C4C     00             DB 00
00401C4D     00             DB 00
00401C4E     00             DB 00
00401C4F     00             DB 00
00401C50     00             DB 00
00401C51     00             DB 00
00401C52     00             DB 00
00401C53     00             DB 00
00401C54     00             DB 00
00401C55     00             DB 00
00401C56     00             DB 00
00401C57     00             DB 00
00401C58     00             DB 00
00401C59     00             DB 00
00401C5A     00             DB 00
00401C5B     00             DB 00
00401C5C     00             DB 00
00401C5D     00             DB 00
00401C5E     00             DB 00
00401C5F     00             DB 00
00401C60     00             DB 00
00401C61     00             DB 00
00401C62     00             DB 00
00401C63     00             DB 00
00401C64     00             DB 00
00401C65     00             DB 00
00401C66     00             DB 00
00401C67     00             DB 00
00401C68     00             DB 00
00401C69     00             DB 00
00401C6A     00             DB 00
00401C6B     00             DB 00
00401C6C     00             DB 00
00401C6D     00             DB 00
00401C6E     00             DB 00
00401C6F     00             DB 00
00401C70     00             DB 00
00401C71     00             DB 00
00401C72     00             DB 00
00401C73     00             DB 00
00401C74     00             DB 00
00401C75     00             DB 00
00401C76     00             DB 00
00401C77     00             DB 00
00401C78     00             DB 00
00401C79     00             DB 00
00401C7A     00             DB 00
00401C7B     00             DB 00
00401C7C     00             DB 00
00401C7D     00             DB 00
00401C7E     00             DB 00
00401C7F     00             DB 00
00401C80     00             DB 00
00401C81     00             DB 00
00401C82     00             DB 00
00401C83     00             DB 00
00401C84     00             DB 00
00401C85     00             DB 00
00401C86     00             DB 00
00401C87     00             DB 00
00401C88     00             DB 00
00401C89     00             DB 00
00401C8A     00             DB 00
00401C8B     00             DB 00
00401C8C     00             DB 00
00401C8D     00             DB 00
00401C8E     00             DB 00
00401C8F     00             DB 00
00401C90     00             DB 00
00401C91     00             DB 00
00401C92     00             DB 00
00401C93     00             DB 00
00401C94     00             DB 00
00401C95     00             DB 00
00401C96     00             DB 00
00401C97     00             DB 00
00401C98     00             DB 00
00401C99     00             DB 00
00401C9A     00             DB 00
00401C9B     00             DB 00
00401C9C     00             DB 00
00401C9D     00             DB 00
00401C9E     00             DB 00
00401C9F     00             DB 00
00401CA0     00             DB 00
00401CA1     00             DB 00
00401CA2     00             DB 00
00401CA3     00             DB 00
00401CA4     00             DB 00
00401CA5     00             DB 00
00401CA6     00             DB 00
00401CA7     00             DB 00
00401CA8     00             DB 00
00401CA9     00             DB 00
00401CAA     00             DB 00
00401CAB     00             DB 00
00401CAC     00             DB 00
00401CAD     00             DB 00
00401CAE     00             DB 00
00401CAF     00             DB 00
00401CB0     00             DB 00
00401CB1     00             DB 00
00401CB2     00             DB 00
00401CB3     00             DB 00
00401CB4     00             DB 00
00401CB5     00             DB 00
00401CB6     00             DB 00
00401CB7     00             DB 00
00401CB8     00             DB 00
00401CB9     00             DB 00
00401CBA     00             DB 00
00401CBB     00             DB 00
00401CBC     00             DB 00
00401CBD     00             DB 00
00401CBE     00             DB 00
00401CBF     00             DB 00
00401CC0     00             DB 00
00401CC1     00             DB 00
00401CC2     00             DB 00
00401CC3     00             DB 00
00401CC4     00             DB 00
00401CC5     00             DB 00
00401CC6     00             DB 00
00401CC7     00             DB 00
00401CC8     00             DB 00
00401CC9     00             DB 00
00401CCA     00             DB 00
00401CCB     00             DB 00
00401CCC     00             DB 00
00401CCD     00             DB 00
00401CCE     00             DB 00
00401CCF     00             DB 00
00401CD0     00             DB 00
00401CD1     00             DB 00
00401CD2     00             DB 00
00401CD3     00             DB 00
00401CD4     00             DB 00
00401CD5     00             DB 00
00401CD6     00             DB 00
00401CD7     00             DB 00
00401CD8     00             DB 00
00401CD9     00             DB 00
00401CDA     00             DB 00
00401CDB     00             DB 00
00401CDC     00             DB 00
00401CDD     00             DB 00
00401CDE     00             DB 00
00401CDF     00             DB 00
00401CE0     00             DB 00
00401CE1     00             DB 00
00401CE2     00             DB 00
00401CE3     00             DB 00
00401CE4     00             DB 00
00401CE5     00             DB 00
00401CE6     00             DB 00
00401CE7     00             DB 00
00401CE8     00             DB 00
00401CE9     00             DB 00
00401CEA     00             DB 00
00401CEB     00             DB 00
00401CEC     00             DB 00
00401CED     00             DB 00
00401CEE     00             DB 00
00401CEF     00             DB 00
00401CF0     00             DB 00
00401CF1     00             DB 00
00401CF2     00             DB 00
00401CF3     00             DB 00
00401CF4     00             DB 00
00401CF5     00             DB 00
00401CF6     00             DB 00
00401CF7     00             DB 00
00401CF8     00             DB 00
00401CF9     00             DB 00
00401CFA     00             DB 00
00401CFB     00             DB 00
00401CFC     00             DB 00
00401CFD     00             DB 00
00401CFE     00             DB 00
00401CFF     00             DB 00
00401D00     00             DB 00
00401D01     00             DB 00
00401D02     00             DB 00
00401D03     00             DB 00
00401D04     00             DB 00
00401D05     00             DB 00
00401D06     00             DB 00
00401D07     00             DB 00
00401D08     00             DB 00
00401D09     00             DB 00
00401D0A     00             DB 00
00401D0B     00             DB 00
00401D0C     00             DB 00
00401D0D     00             DB 00
00401D0E     00             DB 00
00401D0F     00             DB 00
00401D10     00             DB 00
00401D11     00             DB 00
00401D12     00             DB 00
00401D13     00             DB 00
00401D14     00             DB 00
00401D15     00             DB 00
00401D16     00             DB 00
00401D17     00             DB 00
00401D18     00             DB 00
00401D19     00             DB 00
00401D1A     00             DB 00
00401D1B     00             DB 00
00401D1C     00             DB 00
00401D1D     00             DB 00
00401D1E     00             DB 00
00401D1F     00             DB 00
00401D20     00             DB 00
00401D21     00             DB 00
00401D22     00             DB 00
00401D23     00             DB 00
00401D24     00             DB 00
00401D25     00             DB 00
00401D26     00             DB 00
00401D27     00             DB 00
00401D28     00             DB 00
00401D29     00             DB 00
00401D2A     00             DB 00
00401D2B     00             DB 00
00401D2C     00             DB 00
00401D2D     00             DB 00
00401D2E     00             DB 00
00401D2F     00             DB 00
00401D30     00             DB 00
00401D31     00             DB 00
00401D32     00             DB 00
00401D33     00             DB 00
00401D34     00             DB 00
00401D35     00             DB 00
00401D36     00             DB 00
00401D37     00             DB 00
00401D38     00             DB 00
00401D39     00             DB 00
00401D3A     00             DB 00
00401D3B     00             DB 00
00401D3C     00             DB 00
00401D3D     00             DB 00
00401D3E     00             DB 00
00401D3F     00             DB 00
00401D40     00             DB 00
00401D41     00             DB 00
00401D42     00             DB 00
00401D43     00             DB 00
00401D44     00             DB 00
00401D45     00             DB 00
00401D46     00             DB 00
00401D47     00             DB 00
00401D48     00             DB 00
00401D49     00             DB 00
00401D4A     00             DB 00
00401D4B     00             DB 00
00401D4C     00             DB 00
00401D4D     00             DB 00
00401D4E     00             DB 00
00401D4F     00             DB 00
00401D50     00             DB 00
00401D51     00             DB 00
00401D52     00             DB 00
00401D53     00             DB 00
00401D54     00             DB 00
00401D55     00             DB 00
00401D56     00             DB 00
00401D57     00             DB 00
00401D58     00             DB 00
00401D59     00             DB 00
00401D5A     00             DB 00
00401D5B     00             DB 00
00401D5C     00             DB 00
00401D5D     00             DB 00
00401D5E     00             DB 00
00401D5F     00             DB 00
00401D60     00             DB 00
00401D61     00             DB 00
00401D62     00             DB 00
00401D63     00             DB 00
00401D64     00             DB 00
00401D65     00             DB 00
00401D66     00             DB 00
00401D67     00             DB 00
00401D68     00             DB 00
00401D69     00             DB 00
00401D6A     00             DB 00
00401D6B     00             DB 00
00401D6C     00             DB 00
00401D6D     00             DB 00
00401D6E     00             DB 00
00401D6F     00             DB 00
00401D70     00             DB 00
00401D71     00             DB 00
00401D72     00             DB 00
00401D73     00             DB 00
00401D74     00             DB 00
00401D75     00             DB 00
00401D76     00             DB 00
00401D77     00             DB 00
00401D78     00             DB 00
00401D79     00             DB 00
00401D7A     00             DB 00
00401D7B     00             DB 00
00401D7C     00             DB 00
00401D7D     00             DB 00
00401D7E     00             DB 00
00401D7F     00             DB 00
00401D80     00             DB 00
00401D81     00             DB 00
00401D82     00             DB 00
00401D83     00             DB 00
00401D84     00             DB 00
00401D85     00             DB 00
00401D86     00             DB 00
00401D87     00             DB 00
00401D88     00             DB 00
00401D89     00             DB 00
00401D8A     00             DB 00
00401D8B     00             DB 00
00401D8C     00             DB 00
00401D8D     00             DB 00
00401D8E     00             DB 00
00401D8F     00             DB 00
00401D90     00             DB 00
00401D91     00             DB 00
00401D92     00             DB 00
00401D93     00             DB 00
00401D94     00             DB 00
00401D95     00             DB 00
00401D96     00             DB 00
00401D97     00             DB 00
00401D98     00             DB 00
00401D99     00             DB 00
00401D9A     00             DB 00
00401D9B     00             DB 00
00401D9C     00             DB 00
00401D9D     00             DB 00
00401D9E     00             DB 00
00401D9F     00             DB 00
00401DA0     00             DB 00
00401DA1     00             DB 00
00401DA2     00             DB 00
00401DA3     00             DB 00
00401DA4     00             DB 00
00401DA5     00             DB 00
00401DA6     00             DB 00
00401DA7     00             DB 00
00401DA8     00             DB 00
00401DA9     00             DB 00
00401DAA     00             DB 00
00401DAB     00             DB 00
00401DAC     00             DB 00
00401DAD     00             DB 00
00401DAE     00             DB 00
00401DAF     00             DB 00
00401DB0     00             DB 00
00401DB1     00             DB 00
00401DB2     00             DB 00
00401DB3     00             DB 00
00401DB4     00             DB 00
00401DB5     00             DB 00
00401DB6     00             DB 00
00401DB7     00             DB 00
00401DB8     00             DB 00
00401DB9     00             DB 00
00401DBA     00             DB 00
00401DBB     00             DB 00
00401DBC     00             DB 00
00401DBD     00             DB 00
00401DBE     00             DB 00
00401DBF     00             DB 00
00401DC0     00             DB 00
00401DC1     00             DB 00
00401DC2     00             DB 00
00401DC3     00             DB 00
00401DC4     00             DB 00
00401DC5     00             DB 00
00401DC6     00             DB 00
00401DC7     00             DB 00
00401DC8     00             DB 00
00401DC9     00             DB 00
00401DCA     00             DB 00
00401DCB     00             DB 00
00401DCC     00             DB 00
00401DCD     00             DB 00
00401DCE     00             DB 00
00401DCF     00             DB 00
00401DD0     00             DB 00
00401DD1     00             DB 00
00401DD2     00             DB 00
00401DD3     00             DB 00
00401DD4     00             DB 00
00401DD5     00             DB 00
00401DD6     00             DB 00
00401DD7     00             DB 00
00401DD8     00             DB 00
00401DD9     00             DB 00
00401DDA     00             DB 00
00401DDB     00             DB 00
00401DDC     00             DB 00
00401DDD     00             DB 00
00401DDE     00             DB 00
00401DDF     00             DB 00
00401DE0     00             DB 00
00401DE1     00             DB 00
00401DE2     00             DB 00
00401DE3     00             DB 00
00401DE4     00             DB 00
00401DE5     00             DB 00
00401DE6     00             DB 00
00401DE7     00             DB 00
00401DE8     00             DB 00
00401DE9     00             DB 00
00401DEA     00             DB 00
00401DEB     00             DB 00
00401DEC     00             DB 00
00401DED     00             DB 00
00401DEE     00             DB 00
00401DEF     00             DB 00
00401DF0     00             DB 00
00401DF1     00             DB 00
00401DF2     00             DB 00
00401DF3     00             DB 00
00401DF4     00             DB 00
00401DF5     00             DB 00
00401DF6     00             DB 00
00401DF7     00             DB 00
00401DF8     00             DB 00
00401DF9     00             DB 00
00401DFA     00             DB 00
00401DFB     00             DB 00
00401DFC     00             DB 00
00401DFD     00             DB 00
00401DFE     00             DB 00
00401DFF     00             DB 00
00401E00     00             DB 00
00401E01     00             DB 00
00401E02     00             DB 00
00401E03     00             DB 00
00401E04     00             DB 00
00401E05     00             DB 00
00401E06     00             DB 00
00401E07     00             DB 00
00401E08     00             DB 00
00401E09     00             DB 00
00401E0A     00             DB 00
00401E0B     00             DB 00
00401E0C     00             DB 00
00401E0D     00             DB 00
00401E0E     00             DB 00
00401E0F     00             DB 00
00401E10     00             DB 00
00401E11     00             DB 00
00401E12     00             DB 00
00401E13     00             DB 00
00401E14     00             DB 00
00401E15     00             DB 00
00401E16     00             DB 00
00401E17     00             DB 00
00401E18     00             DB 00
00401E19     00             DB 00
00401E1A     00             DB 00
00401E1B     00             DB 00
00401E1C     00             DB 00
00401E1D     00             DB 00
00401E1E     00             DB 00
00401E1F     00             DB 00
00401E20     00             DB 00
00401E21     00             DB 00
00401E22     00             DB 00
00401E23     00             DB 00
00401E24     00             DB 00
00401E25     00             DB 00
00401E26     00             DB 00
00401E27     00             DB 00
00401E28     00             DB 00
00401E29     00             DB 00
00401E2A     00             DB 00
00401E2B     00             DB 00
00401E2C     00             DB 00
00401E2D     00             DB 00
00401E2E     00             DB 00
00401E2F     00             DB 00
00401E30     00             DB 00
00401E31     00             DB 00
00401E32     00             DB 00
00401E33     00             DB 00
00401E34     00             DB 00
00401E35     00             DB 00
00401E36     00             DB 00
00401E37     00             DB 00
00401E38     00             DB 00
00401E39     00             DB 00
00401E3A     00             DB 00
00401E3B     00             DB 00
00401E3C     00             DB 00
00401E3D     00             DB 00
00401E3E     00             DB 00
00401E3F     00             DB 00
00401E40     00             DB 00
00401E41     00             DB 00
00401E42     00             DB 00
00401E43     00             DB 00
00401E44     00             DB 00
00401E45     00             DB 00
00401E46     00             DB 00
00401E47     00             DB 00
00401E48     00             DB 00
00401E49     00             DB 00
00401E4A     00             DB 00
00401E4B     00             DB 00
00401E4C     00             DB 00
00401E4D     00             DB 00
00401E4E     00             DB 00
00401E4F     00             DB 00
00401E50     00             DB 00
00401E51     00             DB 00
00401E52     00             DB 00
00401E53     00             DB 00
00401E54     00             DB 00
00401E55     00             DB 00
00401E56     00             DB 00
00401E57     00             DB 00
00401E58     00             DB 00
00401E59     00             DB 00
00401E5A     00             DB 00
00401E5B     00             DB 00
00401E5C     00             DB 00
00401E5D     00             DB 00
00401E5E     00             DB 00
00401E5F     00             DB 00
00401E60     00             DB 00
00401E61     00             DB 00
00401E62     00             DB 00
00401E63     00             DB 00
00401E64     00             DB 00
00401E65     00             DB 00
00401E66     00             DB 00
00401E67     00             DB 00
00401E68     00             DB 00
00401E69     00             DB 00
00401E6A     00             DB 00
00401E6B     00             DB 00
00401E6C     00             DB 00
00401E6D     00             DB 00
00401E6E     00             DB 00
00401E6F     00             DB 00
00401E70     00             DB 00
00401E71     00             DB 00
00401E72     00             DB 00
00401E73     00             DB 00
00401E74     00             DB 00
00401E75     00             DB 00
00401E76     00             DB 00
00401E77     00             DB 00
00401E78     00             DB 00
00401E79     00             DB 00
00401E7A     00             DB 00
00401E7B     00             DB 00
00401E7C     00             DB 00
00401E7D     00             DB 00
00401E7E     00             DB 00
00401E7F     00             DB 00
00401E80     00             DB 00
00401E81     00             DB 00
00401E82     00             DB 00
00401E83     00             DB 00
00401E84     00             DB 00
00401E85     00             DB 00
00401E86     00             DB 00
00401E87     00             DB 00
00401E88     00             DB 00
00401E89     00             DB 00
00401E8A     00             DB 00
00401E8B     00             DB 00
00401E8C     00             DB 00
00401E8D     00             DB 00
00401E8E     00             DB 00
00401E8F     00             DB 00
00401E90     00             DB 00
00401E91     00             DB 00
00401E92     00             DB 00
00401E93     00             DB 00
00401E94     00             DB 00
00401E95     00             DB 00
00401E96     00             DB 00
00401E97     00             DB 00
00401E98     00             DB 00
00401E99     00             DB 00
00401E9A     00             DB 00
00401E9B     00             DB 00
00401E9C     00             DB 00
00401E9D     00             DB 00
00401E9E     00             DB 00
00401E9F     00             DB 00
00401EA0     00             DB 00
00401EA1     00             DB 00
00401EA2     00             DB 00
00401EA3     00             DB 00
00401EA4     00             DB 00
00401EA5     00             DB 00
00401EA6     00             DB 00
00401EA7     00             DB 00
00401EA8     00             DB 00
00401EA9     00             DB 00
00401EAA     00             DB 00
00401EAB     00             DB 00
00401EAC     00             DB 00
00401EAD     00             DB 00
00401EAE     00             DB 00
00401EAF     00             DB 00
00401EB0     00             DB 00
00401EB1     00             DB 00
00401EB2     00             DB 00
00401EB3     00             DB 00
00401EB4     00             DB 00
00401EB5     00             DB 00
00401EB6     00             DB 00
00401EB7     00             DB 00
00401EB8     00             DB 00
00401EB9     00             DB 00
00401EBA     00             DB 00
00401EBB     00             DB 00
00401EBC     00             DB 00
00401EBD     00             DB 00
00401EBE     00             DB 00
00401EBF     00             DB 00
00401EC0     00             DB 00
00401EC1     00             DB 00
00401EC2     00             DB 00
00401EC3     00             DB 00
00401EC4     00             DB 00
00401EC5     00             DB 00
00401EC6     00             DB 00
00401EC7     00             DB 00
00401EC8     00             DB 00
00401EC9     00             DB 00
00401ECA     00             DB 00
00401ECB     00             DB 00
00401ECC     00             DB 00
00401ECD     00             DB 00
00401ECE     00             DB 00
00401ECF     00             DB 00
00401ED0     00             DB 00
00401ED1     00             DB 00
00401ED2     00             DB 00
00401ED3     00             DB 00
00401ED4     00             DB 00
00401ED5     00             DB 00
00401ED6     00             DB 00
00401ED7     00             DB 00
00401ED8     00             DB 00
00401ED9     00             DB 00
00401EDA     00             DB 00
00401EDB     00             DB 00
00401EDC     00             DB 00
00401EDD     00             DB 00
00401EDE     00             DB 00
00401EDF     00             DB 00
00401EE0     00             DB 00
00401EE1     00             DB 00
00401EE2     00             DB 00
00401EE3     00             DB 00
00401EE4     00             DB 00
00401EE5     00             DB 00
00401EE6     00             DB 00
00401EE7     00             DB 00
00401EE8     00             DB 00
00401EE9     00             DB 00
00401EEA     00             DB 00
00401EEB     00             DB 00
00401EEC     00             DB 00
00401EED     00             DB 00
00401EEE     00             DB 00
00401EEF     00             DB 00
00401EF0     00             DB 00
00401EF1     00             DB 00
00401EF2     00             DB 00
00401EF3     00             DB 00
00401EF4     00             DB 00
00401EF5     00             DB 00
00401EF6     00             DB 00
00401EF7     00             DB 00
00401EF8     00             DB 00
00401EF9     00             DB 00
00401EFA     00             DB 00
00401EFB     00             DB 00
00401EFC     00             DB 00
00401EFD     00             DB 00
00401EFE     00             DB 00
00401EFF     00             DB 00
00401F00     00             DB 00
00401F01     00             DB 00
00401F02     00             DB 00
00401F03     00             DB 00
00401F04     00             DB 00
00401F05     00             DB 00
00401F06     00             DB 00
00401F07     00             DB 00
00401F08     00             DB 00
00401F09     00             DB 00
00401F0A     00             DB 00
00401F0B     00             DB 00
00401F0C     00             DB 00
00401F0D     00             DB 00
00401F0E     00             DB 00
00401F0F     00             DB 00
00401F10     00             DB 00
00401F11     00             DB 00
00401F12     00             DB 00
00401F13     00             DB 00
00401F14     00             DB 00
00401F15     00             DB 00
00401F16     00             DB 00
00401F17     00             DB 00
00401F18     00             DB 00
00401F19     00             DB 00
00401F1A     00             DB 00
00401F1B     00             DB 00
00401F1C     00             DB 00
00401F1D     00             DB 00
00401F1E     00             DB 00
00401F1F     00             DB 00
00401F20     00             DB 00
00401F21     00             DB 00
00401F22     00             DB 00
00401F23     00             DB 00
00401F24     00             DB 00
00401F25     00             DB 00
00401F26     00             DB 00
00401F27     00             DB 00
00401F28     00             DB 00
00401F29     00             DB 00
00401F2A     00             DB 00
00401F2B     00             DB 00
00401F2C     00             DB 00
00401F2D     00             DB 00
00401F2E     00             DB 00
00401F2F     00             DB 00
00401F30     00             DB 00
00401F31     00             DB 00
00401F32     00             DB 00
00401F33     00             DB 00
00401F34     00             DB 00
00401F35     00             DB 00
00401F36     00             DB 00
00401F37     00             DB 00
00401F38     00             DB 00
00401F39     00             DB 00
00401F3A     00             DB 00
00401F3B     00             DB 00
00401F3C     00             DB 00
00401F3D     00             DB 00
00401F3E     00             DB 00
00401F3F     00             DB 00
00401F40     00             DB 00
00401F41     00             DB 00
00401F42     00             DB 00
00401F43     00             DB 00
00401F44     00             DB 00
00401F45     00             DB 00
00401F46     00             DB 00
00401F47     00             DB 00
00401F48     00             DB 00
00401F49     00             DB 00
00401F4A     00             DB 00
00401F4B     00             DB 00
00401F4C     00             DB 00
00401F4D     00             DB 00
00401F4E     00             DB 00
00401F4F     00             DB 00
00401F50     00             DB 00
00401F51     00             DB 00
00401F52     00             DB 00
00401F53     00             DB 00
00401F54     00             DB 00
00401F55     00             DB 00
00401F56     00             DB 00
00401F57     00             DB 00
00401F58     00             DB 00
00401F59     00             DB 00
00401F5A     00             DB 00
00401F5B     00             DB 00
00401F5C     00             DB 00
00401F5D     00             DB 00
00401F5E     00             DB 00
00401F5F     00             DB 00
00401F60     00             DB 00
00401F61     00             DB 00
00401F62     00             DB 00
00401F63     00             DB 00
00401F64     00             DB 00
00401F65     00             DB 00
00401F66     00             DB 00
00401F67     00             DB 00
00401F68     00             DB 00
00401F69     00             DB 00
00401F6A     00             DB 00
00401F6B     00             DB 00
00401F6C     00             DB 00
00401F6D     00             DB 00
00401F6E     00             DB 00
00401F6F     00             DB 00
00401F70     00             DB 00
00401F71     00             DB 00
00401F72     00             DB 00
00401F73     00             DB 00
00401F74     00             DB 00
00401F75     00             DB 00
00401F76     00             DB 00
00401F77     00             DB 00
00401F78     00             DB 00
00401F79     00             DB 00
00401F7A     00             DB 00
00401F7B     00             DB 00
00401F7C     00             DB 00
00401F7D     00             DB 00
00401F7E     00             DB 00
00401F7F     00             DB 00
00401F80     00             DB 00
00401F81     00             DB 00
00401F82     00             DB 00
00401F83     00             DB 00
00401F84     00             DB 00
00401F85     00             DB 00
00401F86     00             DB 00
00401F87     00             DB 00
00401F88     00             DB 00
00401F89     00             DB 00
00401F8A     00             DB 00
00401F8B     00             DB 00
00401F8C     00             DB 00
00401F8D     00             DB 00
00401F8E     00             DB 00
00401F8F     00             DB 00
00401F90     00             DB 00
00401F91     00             DB 00
00401F92     00             DB 00
00401F93     00             DB 00
00401F94     00             DB 00
00401F95     00             DB 00
00401F96     00             DB 00
00401F97     00             DB 00
00401F98     00             DB 00
00401F99     00             DB 00
00401F9A     00             DB 00
00401F9B     00             DB 00
00401F9C     00             DB 00
00401F9D     00             DB 00
00401F9E     00             DB 00
00401F9F     00             DB 00
00401FA0     00             DB 00
00401FA1     00             DB 00
00401FA2     00             DB 00
00401FA3     00             DB 00
00401FA4     00             DB 00
00401FA5     00             DB 00
00401FA6     00             DB 00
00401FA7     00             DB 00
00401FA8     00             DB 00
00401FA9     00             DB 00
00401FAA     00             DB 00
00401FAB     00             DB 00
00401FAC     00             DB 00
00401FAD     00             DB 00
00401FAE     00             DB 00
00401FAF     00             DB 00
00401FB0     00             DB 00
00401FB1     00             DB 00
00401FB2     00             DB 00
00401FB3     00             DB 00
00401FB4     00             DB 00
00401FB5     00             DB 00
00401FB6     00             DB 00
00401FB7     00             DB 00
00401FB8     00             DB 00
00401FB9     00             DB 00
00401FBA     00             DB 00
00401FBB     00             DB 00
00401FBC     00             DB 00
00401FBD     00             DB 00
00401FBE     00             DB 00
00401FBF     00             DB 00
00401FC0     00             DB 00
00401FC1     00             DB 00
00401FC2     00             DB 00
00401FC3     00             DB 00
00401FC4     00             DB 00
00401FC5     00             DB 00
00401FC6     00             DB 00
00401FC7     00             DB 00
00401FC8     00             DB 00
00401FC9     00             DB 00
00401FCA     00             DB 00
00401FCB     00             DB 00
00401FCC     00             DB 00
00401FCD     00             DB 00
00401FCE     00             DB 00
00401FCF     00             DB 00
00401FD0     00             DB 00
00401FD1     00             DB 00
00401FD2     00             DB 00
00401FD3     00             DB 00
00401FD4     00             DB 00
00401FD5     00             DB 00
00401FD6     00             DB 00
00401FD7     00             DB 00
00401FD8     00             DB 00
00401FD9     00             DB 00
00401FDA     00             DB 00
00401FDB     00             DB 00
00401FDC     00             DB 00
00401FDD     00             DB 00
00401FDE     00             DB 00
00401FDF     00             DB 00
00401FE0     00             DB 00
00401FE1     00             DB 00
00401FE2     00             DB 00
00401FE3     00             DB 00
00401FE4     00             DB 00
00401FE5     00             DB 00
00401FE6     00             DB 00
00401FE7     00             DB 00
00401FE8     00             DB 00
00401FE9     00             DB 00
00401FEA     00             DB 00
00401FEB     00             DB 00
00401FEC     00             DB 00
00401FED     00             DB 00
00401FEE     00             DB 00
00401FEF     00             DB 00
00401FF0     00             DB 00
00401FF1     00             DB 00
00401FF2     00             DB 00
00401FF3     00             DB 00
00401FF4     00             DB 00
00401FF5     00             DB 00
00401FF6     00             DB 00
00401FF7     00             DB 00
00401FF8     00             DB 00
00401FF9     00             DB 00
00401FFA     00             DB 00
00401FFB     00             DB 00
00401FFC     00             DB 00
00401FFD     00             DB 00
00401FFE     00             DB 00
00401FFF     00             DB 00

