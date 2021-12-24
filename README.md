# Viking
環境
Unity 2020.3.23f1

遊戲介紹

進入遊戲之後，有三個按鈕，分別為(開始遊戲)(遊戲指引)(離開遊戲)

在遊戲指引中也可以看到<操控方法>的介紹
選擇開始遊戲，進入遊戲畫面，可以看到左方有一個小視角，是後照鏡，可以看到後方追你的怪物離你多遠
遊戲中可以看到金幣，吃下一個，可以加100分

遊戲中的界面上有一個暫停按鈕，裡面有四個按鈕，分別為(回到遊戲)(遊戲指引)(回到開始頁面)(離開遊戲)




操控方法

W 向前移動  A 向左移動  S 向後移動  D 向右移動 
Q 視角左轉90度  E 視角右轉90度
空白鍵跳躍



BONUS

1.有T字路口

2.有背景音樂，死掉也有做慘叫聲

3.覺得很讚的code
我的旋轉用InvokeRepeating，達到緩慢旋轉的效果

下面是旋轉的code:
       
        if (Input.GetKey(KeyCode.E) && canturn)
        {
            canturn = false;    
            InvokeRepeating("turnright",0, 0.01f);
            endturn = true;
        }
        if (Input.GetKey(KeyCode.Q) && canturn)
        {
            canturn = false;
            InvokeRepeating("turnleft", 0, 0.01f);
            endturn = true;
        }
        if (endturn == true)
            turntime += Time.deltaTime;
        if (turntime >= 0.9f)
        {
            CancelInvoke();
            endturn = false;
            turntime = 0;
        }
         if (turnwait > 1f)
        {
            turnwait = 0;
            canturn = true;
        }
    void turnright()
    {
        transform.Rotate(Vector3.up);
    }
    void turnleft()
    {
        transform.Rotate(Vector3.down);
    }
    
    
4.特殊項目

做了一個後照鏡，可以看到敵人距離你多遠





        
  
