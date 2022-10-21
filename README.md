# Nest Js Authz

Tired of spending the first few sprints figuring out basic, or not so basic, authentication for you shiny new NestJs application? So were we!

This repository aspires to be a one-stop-shop for your NestJs authentication and authorization needs.

Features:

- Signup
- Sign-in
- Sign-out
- Password reset workflow
- Jwt, or cookie, based authentication helpers.
- Helpers, decorators for Role based access control.
- Integration with Oso policy language for great power.

Integrate your existing User models with our authentication providers using passport style hooks or, let us manage it. 

## How it works

Add `@tss/nestjs-authz` to an existing nestJs application:
`npm i @tss/nestjs-authz`

Run our tool to prep your repository with the appropriate Orm models.
- TypeOrm
- Prisma 
This step will create the needed 'entity' or 'model' files to work with our supported ORMs.


Import the module.

```
{
    imports: [
      AuthzModule.forRoot(),
    ]
}
```

... This is going to assume a 'fresh' nestJs repository for now. We'll need to work to support refactoring existing systems.

Start using our helpers.

```
import { HasRole } from 'tss/nestjs-authz';

@Controller()
@HasRole('user')
export class MyController{

}
```
