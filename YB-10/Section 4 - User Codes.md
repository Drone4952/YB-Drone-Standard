User Codes are an alternative way to communicate with the drone. You can of course just tell the drone what you want in a sentence, but sometimes you want to be 100% clear on what you want. This is where User Codes come in handy.

# Query Codes
| Code | Meaning                 | Explanation                                      |
| ---- | ----------------------- | ------------------------------------------------ |
| QPS  | Query power status      | Drone reports on its power state                 |
| QSC  | Query subject condition | Drone reports on its subjects condition          |
| QTU  | Query tie up            | Drone reports how it is currently tied up        |
| QCE  | Query current equipment | Drone reports on its equipment (example: collar) |
| QAP  | Query any problems      | Drone reports on any problems it got             |
| QCM  | Query current mode      | Drone reports in what mode it is operating       |
| CJQ  | Query Cron Jobs         | Drone reports on its cron jobs                   | 
| HELP |                         | Drone will send link to this user manual         |

# Instruction Codes
| Code | Meaning                  | Explanation                         | Requirements         |
| ---- | ------------------------ | ----------------------------------- | -------------------- |
| IBA  | Instruct bind arms       | Drone restricts its arms            | How to bind          |
| IBL  | Instruct bind legs       | Drone restricts its legs            | How to bind          |
| IBH  | Instruct bind head       | Drone restricts its head            | How to bind          |
| IGB  | Instruct general bind    | Drone restricts itself              | What to bind and how |
| IRA  | Instruct release arms    | Drone releases its arms             |                      |
| IRL  | Instruct release legs    | Drone releases its legs             |                      |
| IRH  | Instruct release head    | Drone releases its head             |                      |
| IGR  | Instruct general release | Drone releases itself               | What to remove       |
| IFR  | Instruct full release    | Drone removes all binds             |                      |
| IEQ  | Instruct equip           | Drone equips something              | What to equip        |
| IUQ  | Instruct unequip         | Drone unequips something            | What to unequip      | 
| AWT  | Await                    | Drone waits for further user input  |                      |
| CNT  | Continue                 | Drone continues from previous await |                      |

# Cron Job Codes
Cron Jobs are essentially tasks that are carried out frequently (optionally with a set interval).
| Code | Meaning         | Explanation                    | Requirements    |
| ---- | --------------- | ------------------------------ | --------------- |
| CJA  | Cron Job Add    | Adds a Cron Job                | Job Explanation |
| CJR  | Cron Job Remove | Removes a Cron Job             | What to remove  |
| CJQ  | Query Cron Jobs | Drone reports on its cron jobs |                 |
