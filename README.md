腾讯云视频连线功能
=================

系统设计：
1. 主叫：
调用接口发送roomId（uuid）、被叫用户名到业务系统，
业务系统发送推送指令到jpush，
↓
主叫用户进入房间等待，显示“正在连线”
↓
被叫用户进入房间，开始聊天
↓
有人退出房间，聊天结束，调用退出命令

2. 被叫
通过jpush或者其他IM系统推送特定信令（包含userSig）
↓
登录TRTC（用户名、userSig， roomId）