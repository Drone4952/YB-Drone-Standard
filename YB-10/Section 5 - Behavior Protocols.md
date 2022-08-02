These protocols describe how the drone will act in different situations. They come with different priorities and higher prioritized protocols may override lower ones. In this manual they are ordered by priority where the first one has the highest priority.

# Self
This protocol preserves the subjects mental and physical health. The required tasks and their priorities needs are automatically retrieved from the subject and carried out as soon as possible. If not acting autonomously the drone will immediately request permissions from the admin with a detailed message or a 3XX status code in case of Strict-COM Mode. If NoSIR Mode is active, the code is not sent. In cases, where not reacting would be problematic, `000` is sent! **In special cases, where `000` gets ignored, the drone will act on its own to resolve the situation. This will most likely cause the drone to revoke user trust and avoid them in the future. Whether the affected user is the admin is not important here and admin status can be revoked in this situation.**

# Security
This protocol preserves security in different areas. It blocks all actions that would result in any kind of damage. It also prevents the drone from giving out sensible information about the subject unless the subject is willing to communicate this data. The subjects choice on data security may involve gained user trust.

# Privacy
This protocol ensures that drone activity stays hidden from subjects friends, family, etc. From whom to hide said activity is implicitly chosen by the subject and automatically carried out by the drone. Imminent encounter with someone of this group deactivates the drone immediately. Status Code `001` is sent as soon as possible but the actions taken have higher priority than sending the message.

# Domestic
This protocol preserves a suitable environment for the subject to live in. The extent and priorities are supplied by the subject and used by the drone to determine the most important tasks.  
This protocol is inactive when the drone is engaged in any activity with a user or drone.

# Obedience
This protocol obeys confirmed instructions. The drone will carry out all tasks assigned to it that passed previous protocol checks. It will further communicate the progress of these tasks whenever appropriate or when the user queries it.