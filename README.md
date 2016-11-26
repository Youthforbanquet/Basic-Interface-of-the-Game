# Basic-Interface-of-the-Game
package s;

import java.awt.BorderLayout;
import java.awt.CardLayout;
import java.awt.Color;
import java.awt.Font;
import java.awt.Graphics;
import java.awt.TextArea;
import java.awt.event.ActionEvent;
import java.awt.event.ActionListener;

import javax.swing.ImageIcon;
import javax.swing.JButton;
import javax.swing.JFrame;
import javax.swing.JLabel;
import javax.swing.JPanel;
import javax.swing.JTextField;
public class a extends JFrame implements ActionListener{
/**
 * 
 */
private static final long serialVersionUID = 1L;
JPanel cards;

CardLayout CLayout=new CardLayout();

public a(){//主界面

getContentPane().setLayout(new BorderLayout());

JPanel cp=new JPanel();//面板1

JButton bt=new JButton("摇骰子");
JButton b3=new JButton("你做我猜");
JButton b4=new JButton("谁是卧底");
cp.add(bt);
cp.add(b3);
cp.add(b4);
getContentPane().add("North",cp);
cards=new JPanel();
cards.setLayout(CLayout);
JPanel p1=new JPanel(){
        
private static final long serialVersionUID = 1L;

public void paintComponent(Graphics g) {
                ImageIcon icon =
                        new ImageIcon("F:\\java\\test2\\bin\\m.jpg");
                // 图片随窗体大小而变化
                g.drawImage(icon.getImage(), 0, 0,this.getSize().width,this.getSize().height,this);
            }
        };//面板2
        p1.setVisible(false);
p1.setLayout(null);
       
JLabel label = new JLabel("快来感受一波吧，各游戏规则如下。");
label.setBounds(185, 10, 215, 22);
p1.add(label);
TextArea pa = new TextArea();
pa.setBounds(10, 61, 563, 235);
Font font =new Font("宋体",Font.BOLD,15);
pa.setFont(font);
 p1.add(pa);
 pa.setText("\t\t\t\t梭哈\n每位玩家五粒骰子。点数：1>6>5>4>3>2。豹子>顺子>炸弹>葫芦>三条>两对>\n对子 >散牌\n豹子：五个骰子点数一样。"
  + "\n顺子：五个骰子点数连续分布。\n炸弹：四个骰子点数一样。\n葫芦：三个骰子点数一样，余下两个骰子点数同为另一数。\n三条：只有三个骰子点数一样。"
  + "\n两对：由两组同点数骰子组成，外加一单牌。\n对子：五个骰子仅有两个骰子点数一样。\n散牌：五个骰子点数各不一样。\n"
  + "\t\t\t\t789\n每位玩家两粒骰子。每人摇一次即开骰。\n如果两粒骰子点数和是7则加酒。\n如果和是8则喝一半。\n如果和是9则喝全杯。\n"
  +"\t\t\t\t大话\n游戏人数为2人，每人手上有一个骰盅，装有5颗骰子。 游戏开始后，大家\n先摇骰，然后从庄家开始按逆时针的顺序发话，庄家先猜。"
  + "前面的数字代\n表骰子的数目，后面的数字代表骰子面朝上的点数。假设庄家说5个4，\n意思是猜所有人的骰子里，至少有5个骰子是4点。 接下来由下一"
  + "家发话\n，下一家如果觉得庄家不足5个4，可以叫所有人开骰钟看骰子，所叫\n点数的骰子数目够的话（比如有5个4、6个4或更多数目的4），下一\n家"
  + "就输了，反之下一家赢，庄家输，本局结束。 但是，如果下一家相信庄家\n，觉得所有玩家的骰子加起来至少有5个4，那么下一家必须重新叫一组数字\n，这"
  + "一组数字不能比庄家叫的那组数字小，并且其中有个数字比庄家的\n大，比如叫6个4(前面的数字比庄家的大)、5个5(后面的数字比庄家的大)\n都是可以的。"
  + " 至此，下一家操作完毕，由下下家发话，重复进行，直到有玩\n家开盅，本局才结束。"
  + "\n\t\t\t\t抢开\n四个人，猜四个骰盅内的点数和个数，每个骰盅内还是五个骰子。\n如甲乙丙丁四人，那起叫最起码就是四个一，最高可喊到二十个六。大家"
  + "\n依此轮流叫数。甲喊完，乙，然后丙、丁。如果下家不信上一家的叫数，\n可叫大家掀开骰盅。如上家猜对四个人的点数和个数，那就下家罚酒。如\n猜错，"
  + "就上家喝酒。如上家喊：十个五，只要开出的等于或大于十个五，包括\n十一个五、十二个五，上家胜。第二次开局由上局输者先叫数。在广东一带\n还流行抢开"
  + "，除了叫数是依此轮流外，无论哪一人叫数，另外的三人有任何一\n人不信都可要求开。而不再是依次叫开了。"
  + "\n\t\t\t\t拔牙\n在骰盅内放十个骰子。由第一人开始摇骰子，摇完猜骰子点数，此点数指\n的是单个骰子的点数，也就是在1-6 中选择。假设四人为甲乙丙丁。"
  + "\n例：甲先报2，打开骰盅，如有2点的骰子，就把该点骰子拿走，\n如十个骰子里有两个是两点就拿走两个，三个就拿走三个。并由下一人乙\n摇骰盅，乙如摇玩筛"
  + "钟猜中骰盅内的点数，拿走猜中的骰子，继续由丙骰。反\n之，如甲报出的点数在十个骰子中都没有，就罚酒一杯。罚完酒后还是由甲继\n续摇 "
  + "骰子，除非甲摇完骰盅后，猜出的点数在骰子里产生，否\n则继续由甲罚酒一杯。此玩法越往后，骰子的数目就越少，猜中\n的概率就越小。在剩下最后一个筛子时，"
  + "第一轮结束。然后重新放入十粒筛\n子，重新开始。该玩法在剩五个以下筛子时，运气不好的人能连续喝\n十几杯酒。");
JPanel p2=new JPanel(){
           
private static final long serialVersionUID = 1L;

public void paintComponent(Graphics g) {
                ImageIcon icon =
                        new ImageIcon("F:\\java\\test2\\bin\\m1.jpg");
                // 图片随窗体大小而变化
                g.drawImage(icon.getImage(), 0, 0,this.getSize().width,this.getSize().height,this);
            }
        };
p2.setLayout(null);
JLabel n=new JLabel("请输入玩家数");
n.setBounds(85, 9, 93, 15);
n.setForeground(Color.red);
p2.add(n);
JTextField t1=new JTextField(10);
t1.setBounds(188, 6, 66, 21);
t1.setText("0"); //把文本框清零  
      t1.setHorizontalAlignment(JTextField.RIGHT);  //文本对齐右边 
p2.add(t1);
JLabel m=new JLabel("请输入骰子数");
m.setBounds(323, 9, 87, 15);
m.setForeground(Color.red);
p2.add(m);
JTextField t2=new JTextField(10);
t2.setBounds(420, 6, 66, 21);
t2.setText("0"); //把文本框清零  
      t2.setHorizontalAlignment(JTextField.RIGHT);  //文本对齐右边 
p2.add(t2);
JButton b=new JButton("摇一摇");
b.setBounds(247, 49, 93, 23);
p2.add(b);
TextArea ja = new TextArea();
ja.setBounds(37, 76, 509, 231);
Font font1 =new Font("宋体",Font.BOLD,12);
ja.setFont(font1);


       p2.add(ja);
b.addActionListener(new ActionListener() {//掷骰子
public void actionPerformed(ActionEvent e) {
  ja.setText("");
  int sum = 0;
for(int i=0;i<Double.parseDouble(t1.getText().trim());i++){
ja.append("第"+(i+1)+"位玩家掷出的骰子为："+"\r\n");
for(int m=0;m<Double.parseDouble(t2.getText().trim());m++){
int g=1+(int)(6*Math.random());
ja.append("\t第"+(m+1)+"粒"+g+"\n");

sum+=g;
if( m> (Double.parseDouble(t2.getText().trim())-2)){
ja.append("\t总数为"+sum+"\n");
sum=0;
}
}
}
}
});
 JButton b5=new JButton("返回");
 b5.setBounds(259, 313, 72, 23);
        p2.add(b5);
     JPanel p3=new JPanel(){
         
private static final long serialVersionUID = 1L;

public void paintComponent(Graphics g) {
              ImageIcon icon =
                      new ImageIcon("F:\\java\\test2\\bin\\m2.jpg");
              // 图片随窗体大小而变化
              g.drawImage(icon.getImage(), 0, 0,this.getSize().width,this.getSize().height,this);
          }
      };//面板4
    JLabel l= new JLabel("你做我猜");
    l.setBounds(256, 0, 64, 22);
    l.setFont(new   java.awt.Font("Dialog",   1,   15)); 
    l.setForeground(Color.red);
     JButton b1=new JButton("开始");
     b1.setBounds(413, 65, 71, 23);
     JTextField c=new JTextField(20);
     c.setBounds(379, 154, 146, 21);
     Font font4 =new Font("宋体",Font.BOLD,12);
c.setFont(font4);
     b1.addActionListener(new ActionListener() {//随机生成词语
public void actionPerformed(ActionEvent e) {
String ciyu[]={"大象","敲门","西瓜","举重","手机","打嗝","牙疼","嗑瓜子","蹲下","灭火器",
"孙悟空","猩猩","吃面条","香蕉","拍球","拳击","睡觉","打麻将","雨伞","主持人","刮胡子","刷牙","企鹅","乒乓球","唇膏","武术","升国旗","长颈鹿","鸭子","游泳","榴莲","遛狗","喝水","扔铅球","遥控器","高跟鞋",
"眼睫毛","拍马屁","骑马","跳绳","系鞋带","篮球","拔河","扭秧歌","照镜子","奥特曼","捡钱包","放风筝","金鸡独立","鸡犬不宁","垂头丧气","一刀两断","哑口无言","左顾右盼","直升飞机","东张西望","三长两短","心口如一","大摇大摆","龟兔赛跑","目瞪口呆","眉飞色舞",
"满地找牙","五体投地","一无所有","睡眼朦胧","比翼双飞","一瘸一拐","闻鸡起舞","一手遮天","捧腹大笑","心急如焚","狼吞虎咽","花枝招展","七零八落","鸡飞狗跳","张牙舞爪","抓耳挠腮","嬉皮笑脸","连滚带爬","张牙舞爪","婀娜多姿","挥汗如雨","纸上谈兵", "含情脉脉","望梅止渴","一针见血","大手大脚","左右为难","虎头蛇尾"};
c.setText(ciyu[(int)(91*Math.random())]);
}   
});
     p3.setLayout(null);
     p3.add(l);
     p3.add(b1);
     
    
     TextArea g= new TextArea("当你点击开始按钮时，\n会随机出现一个词（这\n个词不能让你的队友知\n道）。你需要向你的队\n友通过语言或动作描述\n这个词，当你用语言描\n述时不能出现和词中任\n何字相同的字包括读音\n。否则算作失败！",10,20);
     g.setBounds(10, 28, 235, 200);
    Font font2 =new Font("宋体",Font.BOLD,18);
g.setFont(font2);
p3.add(g);
p3.add(c);
 
     JPanel p4=new JPanel(){
         
private static final long serialVersionUID = 1L;

public void paintComponent(Graphics g) {
              ImageIcon icon =
                      new ImageIcon("F:\\java\\test2\\bin\\m3.jpg");
              // 图片随窗体大小而变化
              g.drawImage(icon.getImage(), 0, 0,this.getSize().width,this.getSize().height,this);
          }
      };//面板5
    JLabel l2 =new JLabel("谁是卧底");
    l2.setBounds(257, 10, 61, 15);
    l2.setForeground(Color.red);
    JLabel l3 =new JLabel("请输入玩家数");
    l3.setBounds(243, 35, 86, 15);
    l3.setForeground(Color.red);
     p4.setLayout(null);
     p4.add(l2);
     p4.add(l3);
     JTextField d=new JTextField(25);
     d.setBounds(200, 60, 156, 21);
     d.setHorizontalAlignment(JTextField.RIGHT);  //文本对齐右边 
     JButton b2=new JButton("开始");
     b2.setBounds(248, 91, 70, 23);
     JTextField f=new JTextField(35);
     f.setBounds(119, 124, 321, 24);
     Font font3 =new Font("宋体",Font.BOLD,15);
f.setFont(font3);
     b2.addActionListener(new ActionListener() {//随机生成词语
public void actionPerformed(ActionEvent e) {
f.setText("");
 
String wodi[]={"浴缸，鱼缸（卧底）","电动车,摩托车（卧底）","眉毛,睫毛（卧底）","书,本（卧底）","筷子,竹签（卧底）","麻雀,乌鸦（卧底）","火车,轮船（卧底）","镜子,玻璃（卧底）","手,脚（卧底）","扫帚,拖把（卧底）","铅笔盒,铅笔带（卧底）"
,"那英,王菲（卧底）","盗墓笔记,鬼吹灯（卧底）","散文,小说（卧底）","树枝,树干（卧底）","脸盆,水桶（卧底）","直尺,三角板（卧底）","吴昕,谢娜（卧底）","晨光,真彩（卧底）","蒙牛,伊利（卧底）","可口可乐,百事可乐（卧底）","加多宝,王老吉（卧底）","门诊,急诊（卧底）"
,"董永,许仙（卧底）","辣椒,芥末（卧底）","唇膏,口红（卧底）","首尔,东京（卧底）","面包,蛋糕（卧底）","同学,同桌（卧底）","作家,编剧（卧底）","作文,论文（卧底）","警察,捕快（卧底）","婚纱,喜服（卧底）","富二代,高富帅（卧底）","魔术师,魔法师（卧底）","手机,座机（卧底）"
,"鸭舌帽,遮阳帽（卧底）","成吉思汗,努尔哈赤（卧底）","鱼香肉丝,四喜丸子（卧底）","小笼包,灌汤包（卧底）","降龙十八掌,九阴白骨爪（卧底）","红烧牛肉面,香辣牛肉面（卧底）","美人心计,倾世皇妃（卧底）","天天向上,非诚勿扰（卧底）","生活费,零花钱（卧底）","神雕侠侣,天龙八部（卧底）","蜘蛛侠,蝙蝠侠（卧底）","牛肉干,猪肉脯（卧底）"} ;
f.setText("第"+(1+(int)(Double.parseDouble(d.getText().trim())*Math.random()))+"位是卧底---"+wodi[(int)(48*Math.random())]);
}   
});
     p4.add(d);
     p4.add(b2);
     p4.add(f);
     
cards.add("Panel with Label and Button",p1);//面板加到cards
cards.add("Panel with Button and Field",p2);
cards.add("你做我猜",p3);

JButton b6 = new JButton("\u8FD4\u56DE");

b6.setBounds(249, 313, 71, 23);
p3.add(b6);
cards.add("谁是卧底",p4);

JButton b7 = new JButton("\u8FD4\u56DE");

b7.setBounds(243, 313, 78, 23);
p4.add(b7);
getContentPane().add("Center",cards);
 bt.addActionListener(new ActionListener() {//随机生成词语
public void actionPerformed(ActionEvent e) {
cp.setVisible(false);
p1.setVisible(false);
p2.setVisible(true);
}   
});
 b3.addActionListener(new ActionListener() {//随机生成词语
public void actionPerformed(ActionEvent e) {
cp.setVisible(false);
p1.setVisible(false);
p2.setVisible(false);
p3.setVisible(true);
}   
});
 b4.addActionListener(new ActionListener() {//随机生成词语
public void actionPerformed(ActionEvent e) {
cp.setVisible(false);
p1.setVisible(false);
p2.setVisible(false);
p3.setVisible(false);
p4.setVisible(true);
}   
});
 b5.addActionListener(new ActionListener() {//随机生成词语
public void actionPerformed(ActionEvent e) {
cp.setVisible(true);
p1.setVisible(false);
p2.setVisible(false);
p3.setVisible(false);
p4.setVisible(false);
}   
});
 b6.addActionListener(new ActionListener() {//随机生成词语
public void actionPerformed(ActionEvent e) {
cp.setVisible(true);
p1.setVisible(false);
p2.setVisible(false);
p3.setVisible(false);
p4.setVisible(false);
}   
});
 b7.addActionListener(new ActionListener() {//随机生成词语
public void actionPerformed(ActionEvent e) {
cp.setVisible(true);
p1.setVisible(false);
p2.setVisible(false);
p3.setVisible(false);
p4.setVisible(false);
}   
});
}

  
   
  
public static void main(String args[]){
a window=new a();
window.setTitle("酒桌小游戏");
window.pack();
window.setDefaultCloseOperation(JFrame.EXIT_ON_CLOSE);
window.setVisible(true);
window.setResizable(false);
window.setSize(600,400);
}




@Override
public void actionPerformed(ActionEvent arg0) {
// TODO Auto-generated method stub

}
}
