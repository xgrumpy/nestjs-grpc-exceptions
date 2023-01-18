# NestJS gRPC Exceptions

This library provides `RpcException` wrappers for gRPC status codes.

### Install

```bash
pnpm add nestjs-grpc-exceptions
```

or

```bash
npm install nestjs-grpc-exceptions
```

or

```bash
yarn add nestjs-grpc-exceptions
```

### Usage:

First add the **GrpcServerExceptionFilter** to your gRPC server:

```ts
import { Module } from "@nestjs/common";
import { APP_FILTER } from "@nestjs/core";
import { GrpcServerExceptionFilter } from "nestjs-grpc-exceptions";

@Module({
  providers: [
    {
      provide: APP_FILTER,
      useClass: GrpcServerExceptionFilter,
    },
  ],
})
export class UserModule {}
```

Now you can use the exception classes:

```ts
throw new GrpcNotFoundException("User Not Found.");
throw new GrpcInvalidArgumentException("input 'name' is not valid.");
```

### ALERT 🚨

This library is in its early development. Be careful about using it in a production environment.
