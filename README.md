# Panic Help Desk
This package is a ticketing system for [Laravel 5](https://laravel.com/) based on [Ticketit](https://github.com/thekordy/ticketit), a very polish written ticketing system package that we fell in love with, so we used it as a base of our project. If you need to make a very customized ticketing project you should check it out; you probably won't find any better starting point.

## Ticketit features
Ticketit has three user roles: Users (from Laravel integrated auth), agents and admins. Admins can create categories for tickets and assign agents to them. You can create tickets via form and attach screenshots to them. Users can list and view their open tickets and communicate with agent through a comment form. It also has statistics and a very flexible configuration system.

Ticketit developers currently have stopped major changes in current release and, from many moths ago, they're planning a new version of the package with more focus on developers.

## PanicHD current features
We've added the following features to ticketit package:
* Tag system: Each category can have it's own tag list. Agents can assign tags to tickets.
* File attachments: For ticket or comment. List images separately and view them in a javascript gallery. Images can also be cropped. All attached files can be renamed and have a description.
* Intervention field that can interact with comments. Description and intervention are also visible and searchable on ticket list.
* Interactive ticket creation form: Admin, of course, always sees all fields in ticket form, but for user and agent roles, any user sees user or agent fields depending on chosen category in the form.
* Department notices: This is a partially developed feature. It deppends on an externally managed department structure not editable within our package. Users are related to persons that have an assigned department. You can assign a "department user" to a specific department (or to all departments option), which may be understood as a fake user account that is linked to the department (and owns the department email). When you create a ticket and you specify an owner wich is a "department user", there will happen two things that do the magic:
  + An email will be sent to "department user" containing the ticket information
  + All real users on the "department user" department or related ones will view this open ticket as a "notice" in the notices panel, just over the new ticket form.
* Ticket calendar: You can specify a start date and a limit date for a ticket. With a combination of this fields, you bring tickets in many different situations deppending on their calendar status, that you can filter and control, like:
  + Tickets that are scheduled to some day in the future (this thurdsay? this month?)
  + Tickets that end today or tomorrow
  + Tickets that already expired
  + Tickets that were just added and started some weeks ago
* Ticket filters: You can filter the ticket list by many different criteria in a specific filters panel: Calendar, category and agent. Of course you still can make an even more specific filter within the ticket list thanks to Datatables engine.
* Agent as a user: Agent may be a user on some categories and a manager on others, so we added a button to let them change their point of view, from agent to user and vice-versa.
